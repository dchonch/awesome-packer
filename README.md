# Awesome Packer [![Awesome](https://awesome.re/badge-flat.svg)](https://github.com/sindresorhus/awesome)

[HashiCorp Packer](https://developer.hashicorp.com/packer) is an open source tool for creating identical machine images across multiple platforms from a single source configuration.

> **Note:** In August 2023, HashiCorp relicensed Packer from MPL 2.0 to the [Business Source License (BSL 1.1)](https://www.hashicorp.com/bsl).

_Please read the [contributing guidelines](contributing.md) before contributing._

## Contents

- [Official Resources](#official-resources)
- [Documentation & Tutorials](#documentation--tutorials)
- [Cloud Builders](#cloud-builders)
- [Provisioners & Tools](#provisioners--tools)
- [Community](#community)

## Official Resources

- [Packer Documentation](https://developer.hashicorp.com/packer/docs) - Complete reference for builders, provisioners, and templates.
- [Packer Integrations Registry](https://developer.hashicorp.com/packer/integrations) - Official plugins and integrations.
- [Packer GitHub](https://github.com/hashicorp/packer) - Source code and issue tracking.
- [HCP Packer](https://developer.hashicorp.com/hcp/docs/packer) - HashiCorp's cloud service for artifact management.

## Documentation & Tutorials

- [HCL2 Template Syntax](https://developer.hashicorp.com/packer/docs/templates/hcl_templates) - Modern template language (standard since v1.7.0).
- [Packer Tutorials](https://developer.hashicorp.com/packer/tutorials) - Hands-on guides for AWS, Azure, GCP, and Docker.
- [Build a Golden Image Pipeline](https://developer.hashicorp.com/packer/tutorials/cloud-production/golden-image-with-hcp-packer) - End-to-end HCP Packer workflow.

## Cloud Builders

- [AWS (EC2)](https://developer.hashicorp.com/packer/integrations/hashicorp/amazon) - Build AMIs with amazon-ebs, amazon-instance, or amazon-chroot.
- [Azure](https://developer.hashicorp.com/packer/integrations/hashicorp/azure) - Build managed images and Shared Image Gallery versions.
- [Google Cloud](https://developer.hashicorp.com/packer/integrations/hashicorp/googlecompute) - Build Compute Engine images.
- [VMware vSphere](https://developer.hashicorp.com/packer/integrations/vmware/vsphere) - Build vSphere templates (maintained by VMware).

## Provisioners & Tools

- [Ansible](https://developer.hashicorp.com/packer/integrations/hashicorp/ansible) - Run Ansible playbooks during builds.
- [Shell](https://developer.hashicorp.com/packer/docs/provisioners/shell) - Execute shell scripts and inline commands.
- [File](https://developer.hashicorp.com/packer/docs/provisioners/file) - Upload files and directories.
- [packer-plugin-sdk](https://github.com/hashicorp/packer-plugin-sdk) - Go SDK for building custom plugins.

## Community

- [HashiCorp User Groups](https://www.meetup.com/pro/hugs) - Local meetup communities.
- [Stack Overflow](https://stackoverflow.com/questions/tagged/packer) - Q&A for Packer.
- [HashiCorp Discuss](https://discuss.hashicorp.com/c/packer) - Official forums.
