# Awesome Packer [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources for [HashiCorp Packer](https://developer.hashicorp.com/packer) — the open source tool for creating identical machine images across multiple platforms from a single source configuration.
>
> Inspired by [@sindresorhus](https://github.com/sindresorhus)'s [awesome](https://github.com/sindresorhus/awesome) and [awesome-terraform](https://github.com/shuaibiyy/awesome-terraform).
>
> Your [contributions](https://github.com/dawitnida/awesome-packer/blob/master/.github/CONTRIBUTING.md) are welcome!

> **Note:** In August 2023, HashiCorp relicensed Packer from MPL 2.0 to the [Business Source License (BSL 1.1)](https://www.hashicorp.com/bsl). The source code remains publicly available; production use by competing vendors is restricted. There is currently no community fork equivalent to Packer.

---

## Contents

- [Official Resources](#official-resources)
- [What's New in 2024–2026](#whats-new-in-20242026)
- [HCL2 Templates](#hcl2-templates)
- [HCP Packer](#hcp-packer)
- [Integrations](#integrations)
- [Plugin Development](#plugin-development)
- [Community Plugins & Tools](#community-plugins--tools)
- [CI/CD Integrations](#cicd-integrations)
- [Tutorials & Blog Posts](#tutorials--blog-posts)
- [Books](#books)
- [Talks & Videos](#talks--videos)
- [Community](#community)

---

## Official Resources

- [Packer Documentation](https://developer.hashicorp.com/packer/docs) - Full reference docs including builders, provisioners, and post-processors.
- [Packer Integrations Registry](https://developer.hashicorp.com/packer/integrations) - Official registry of all supported plugins and integrations.
- [Packer GitHub](https://github.com/hashicorp/packer) - Source code and issue tracker.
- [Packer Release Notes](https://developer.hashicorp.com/packer/docs/release-notes) - Changelog for every Packer version.
- [HashiCorp Packer Blog](https://www.hashicorp.com/blog/category/packer) - Official announcements and release posts.
- [HashiCorp Discuss — Packer](https://discuss.hashicorp.com/c/packer) - Official community forum for questions and announcements.

## What's New in 2024–2026

Packer v1.15 released in March 2026 adds native Linux ARM64 support, multi-file `packer fmt` formatting, and improved plugin loading reliability.

HCP Packer received significant updates: Software Bill of Materials (SBOM) storage is now generally available (HashiConf 2025), and CI/CD pipeline metadata tracking from GitHub, GitLab, Bitbucket, and Jenkins has been GA since HashiConf 2024. The platform adopted v2 nomenclature — Iterations renamed to Versions, Images renamed to Artifacts — and bucket-level RBAC is now available.

Starting August 2025, official HashiCorp-maintained plugins are distributed from `releases.hashicorp.com` instead of GitHub Releases. Packer v1.14.0+ handles this automatically with no user action required.

HCL2 became the standard template format in v1.7.0. JSON templates are still supported but receive no new features. Use `packer hcl2_upgrade` to migrate existing templates.

## HCL2 Templates

Packer v1.7.0+ made HCL2 the standard template format. JSON templates remain supported but are considered legacy and receive no new features.

- [HCL2 Template Syntax](https://developer.hashicorp.com/packer/docs/templates/hcl_templates) - Official reference for writing Packer templates in HCL2.
- [Differences Between HCL2 and JSON Templates](https://developer.hashicorp.com/packer/docs/templates/json_to_hcl) - Side-by-side comparison and migration notes.
- [Upgrade JSON Templates to HCL2](https://developer.hashicorp.com/packer/tutorials/configuration-language/hcl2-upgrade) - Tutorial using the `packer hcl2_upgrade` migration command.
- [Variables in HCL2](https://developer.hashicorp.com/packer/docs/templates/hcl_templates/variables) - Input variables, local values, and environment variable integration.

## HCP Packer

HCP Packer is HashiCorp's cloud service for tracking and managing Packer build artifacts across your organization. Available in Essentials (free) and Standard (paid) editions.

- [HCP Packer Overview](https://developer.hashicorp.com/hcp/docs/packer) - What HCP Packer is and how it fits into the image management lifecycle.
- [Build a Golden Image Pipeline](https://developer.hashicorp.com/packer/tutorials/cloud-production/golden-image-with-hcp-packer) - End-to-end tutorial for managing base images with HCP Packer.
- [HCP Terraform Run Task](https://developer.hashicorp.com/packer/tutorials/hcp/setup-hcp-terraform-run-task) - Block Terraform runs that reference revoked or outdated Packer artifacts.
- [Integrate HCP Packer with Ansible](https://developer.hashicorp.com/validated-patterns/packer/integrate-hcp-packer-with-ansible-automation-platform) - Use HCP Packer artifacts as inputs to Ansible Automation Platform workflows.
- [CI/CD Pipeline Metadata Tracking](https://www.hashicorp.com/blog/hcp-packer-now-tracks-ci-cd-pipeline-metadata) - Track GitHub, GitLab, Bitbucket, and Jenkins pipeline context alongside each artifact.

## Integrations

Official Packer integrations for major platforms. Full list at the Packer Integrations Registry linked in Official Resources.

### Cloud Providers

- [AWS (Amazon EC2)](https://developer.hashicorp.com/packer/integrations/hashicorp/amazon) - Build AMIs using `amazon-ebs`, `amazon-instance`, or `amazon-chroot` builders.
- [Azure (Resource Manager)](https://developer.hashicorp.com/packer/integrations/hashicorp/azure) - Build managed images and Shared Image Gallery versions on Azure.
- [Google Cloud (googlecompute)](https://developer.hashicorp.com/packer/integrations/hashicorp/googlecompute) - Build custom images for Google Compute Engine.
- [DigitalOcean](https://developer.hashicorp.com/packer/integrations/digitalocean/digitalocean) - Build DigitalOcean snapshots.

### Virtualization & Local

- [VMware vSphere](https://developer.hashicorp.com/packer/integrations/vmware/vsphere) - Build vSphere templates using `vsphere-iso` and `vsphere-clone` builders (maintained by VMware, Windows Server 2025 verified).
- [Docker](https://developer.hashicorp.com/packer/integrations/hashicorp/docker) - Build and export Docker images using Packer.
- [QEMU](https://developer.hashicorp.com/packer/integrations/hashicorp/qemu) - Build QEMU/KVM disk images.
- [VirtualBox](https://developer.hashicorp.com/packer/integrations/hashicorp/virtualbox) - Build VirtualBox OVF/OVA images.
- [Vagrant](https://developer.hashicorp.com/packer/integrations/hashicorp/vagrant) - Build and export Vagrant boxes via the `vagrant` builder or post-processor.

### Provisioners

- [Ansible](https://developer.hashicorp.com/packer/integrations/hashicorp/ansible) - Run Ansible playbooks during image builds via `ansible` or `ansible-local` provisioner.
- [Chef](https://developer.hashicorp.com/packer/integrations/chef/chef) - Run Chef recipes during image builds.
- [Shell](https://developer.hashicorp.com/packer/docs/provisioners/shell) - Run shell scripts; supports inline commands and shebang lines (v1.13+).
- [File](https://developer.hashicorp.com/packer/docs/provisioners/file) - Upload files and directories to the image.
- [PowerShell](https://developer.hashicorp.com/packer/docs/provisioners/powershell) - Run PowerShell scripts for Windows image provisioning.

## Plugin Development

Packer plugins are standalone Go programs that communicate with Packer over RPC. All plugin types (builders, provisioners, post-processors, data sources) use the same SDK.

- [Plugin Development Overview](https://developer.hashicorp.com/packer/docs/plugins/creation) - Concepts, architecture, and getting started.
- [packer-plugin-sdk](https://github.com/hashicorp/packer-plugin-sdk) - Official Go SDK for building Packer plugins.
- [packer-plugin-scaffolding](https://github.com/hashicorp/packer-plugin-scaffolding) - Template repo with boilerplate code, CI, and release configuration to bootstrap a new plugin.
- [Install Plugins](https://developer.hashicorp.com/packer/docs/plugins/install) - How `packer init` discovers and installs plugins from the registry.
- [Upgrading Plugins to SDK v2](https://developer.hashicorp.com/packer/guides/1.7-plugin-upgrade) - Migration guide for plugin authors moving to the current SDK.

## Community Plugins & Tools

- [packer-community](https://github.com/packer-community) - GitHub organization hosting community-maintained Packer plugins and tools.
- [vmware/packer-examples-for-vsphere](https://github.com/vmware/packer-examples-for-vsphere) - Official VMware examples for building vSphere templates with Packer and Ansible (HCL2).
- [Racker](https://github.com/aspring/racker) - Ruby DSL for generating Packer JSON templates.
- [packer-provisioner-deno](https://github.com/dontlaugh/packer-provisioner-deno) - Use Deno (TypeScript/JavaScript) for provisioning steps.

> Community plugins are not maintained or tested by HashiCorp. Check repository activity before adopting.

## CI/CD Integrations

- [GitHub Actions](https://developer.hashicorp.com/packer/tutorials/cloud-production/github-actions) - Official tutorial for running Packer builds and pushing metadata to HCP Packer from GitHub Actions.
- [GitLab CI/CD (2024 guide)](https://mpoore.io/posts/2024/using-gitlab-ci-cd-to-automate-my-packer-builds/) - Community walkthrough for automating Packer builds with GitLab runners.
- [GitLab CI/CD Pipelines for Packer](https://virtualhobbit.com/2020/05/05/using-gitlab-ci-cd-pipelines-to-automate-your-hashicorp-packer-builds/) - Step-by-step GitLab automation guide.
- [Google Cloud Build](https://cloud.google.com/build/docs/building/build-vm-images-with-packer) - Use Packer within Google Cloud Build to create Compute Engine images.

## Tutorials & Blog Posts

- [Packer Tutorials](https://developer.hashicorp.com/packer/tutorials) - Official HashiCorp tutorials covering AWS, Azure, GCP, Docker, and more.
- [Automate AMI Creation with Packer](https://devopscube.com/packer-tutorial-for-beginners/) - Beginner-friendly guide to building AWS AMIs (updated February 2026).
- [Getting Started with Packer in 2024](https://dev.to/miry/getting-started-with-packer-in-2024-56d5) - Covers cloud-init setup and JSON-to-HCL2 migration.
- [Windows Server 2025 Packer Build for VMware vSphere](https://www.virtualizationhowto.com/2024/11/windows-server-2025-packer-build-for-vmware-vsphere/) - Build Windows Server 2025 images for vSphere using HCL2.
- [Build EC2 Images with Packer and Ansible](https://medium.com/devopslinks/build-your-own-ec2-machine-images-with-packer-ansible-on-aws-for-immutable-aws-deployments-f7dbe81934a1) - AMI automation combined with Ansible configuration management.

## Books

- [The Packer Book](https://packerbook.com/) - Community book covering Packer fundamentals, templates, and provisioners.
- [AWS SysOps Cookbook, 2nd Edition](https://www.oreilly.com/library/view/aws-sysops-cookbook/9781838550189/) - Includes a dedicated chapter on creating machine images with Packer. (O'Reilly, 2020)

> No dedicated Packer books have been published since 2021. Current knowledge is primarily distributed through official documentation and community tutorials.

## Talks & Videos

- [HashiConf 2025: Scale Infrastructure with New Terraform and Packer Features](https://www.hashicorp.com/blog/scale-infrastructure-with-new-terraform-and-packer-features-at-hashiconf-2025) - SBOM GA, Package Visibility beta, and HCP Packer updates.
- [HashiConf 2024: Terraform, Packer, Nomad, and Waypoint Updates](https://www.hashicorp.com/blog/terraform-packer-nomad-and-waypoint-updates-help-scale-ilm-at-hashiconf-2024) - CI/CD metadata tracking and bucket-level RBAC announcements.
- [HashiCorp Packer Resources Library](https://www.hashicorp.com/resources?product=Packer) - All HashiCorp-published talks, webinars, and whitepapers on Packer.
- [Building Automated Pipelines for Infrastructure Code with Terraform and Packer](https://youtu.be/4uxUScFWzPc) - Conference talk on combining Terraform and Packer.
- [Using Terraform, Packer, and Ansible Together](https://youtu.be/pkEezNSFWtA) - DevOps OKC talk by Aaron Krauss.
- [Packer at Pinterest](https://youtu.be/L-DMwEN_mUk) - How Pinterest scaled machine image creation with Packer.

## Community

- [HashiCorp User Groups (HUGs)](https://www.meetup.com/pro/hugs) - Local meetup groups focused on the HashiCorp ecosystem.
- [StackExchange DevOps — \[packer\]](https://devops.stackexchange.com/questions/tagged/packer) - Q&A on DevOps Stack Exchange.
- [Stack Overflow — \[packer\]](https://stackoverflow.com/questions/tagged/packer) - General Packer scripting and configuration questions.
