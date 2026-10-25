# Hi, I'm Siva Sai Krishna Suryadevara

**Senior Cloud Platform & DevOps Architect @ Evinova (AstraZeneca) · IEEE Senior Member**

I build guardrails for AI in software delivery: sandboxed runtimes that let LLM agents touch
infrastructure safely, CI/CD pipelines that diagnose and repair their own failures, and
policy-as-code that keeps regulated cloud environments compliant.

## Featured work

| Repository | What it does |
| --- | --- |
| [docker-mcp-guardian](https://github.com/SivaSaiKrishnaSuryadevara/docker-mcp-guardian) | MCP server that gives Claude and other agents read-mostly access to Docker: read-only by default, deny-listed restarts resolved by canonical name, secrets redacted. 47 tests. |
| [docker-ci-gatekeeper](https://github.com/SivaSaiKrishnaSuryadevara/docker-ci-gatekeeper) | Self-healing Docker CI step: parses BuildKit failures into a typed taxonomy, asks Claude Code for a minimal fix, verifies it with a rebuild. Hard cap of 2 attempts; fixes are staged, never applied blind. |
| [docker-multiarch-builder](https://github.com/SivaSaiKrishnaSuryadevara/docker-multiarch-builder) | Benchmark of QEMU emulation vs native Buildx nodes for multi-arch images. Measured: emulated arm64 builds ran ~16x slower; emulated amd64 on ARM crashed or hung in 5 of 5 runs. Raw data included. |
| [predictive-cicd-remediation](https://github.com/SivaSaiKrishnaSuryadevara/predictive-cicd-remediation) | Prototype of the system in my Indian patent application 202641038921: LLM-based prediction and automated remediation of CI/CD failures. |
| [zero-trust-cloud-governance-pac](https://github.com/SivaSaiKrishnaSuryadevara/zero-trust-cloud-governance-pac) | Reference policy-as-code architecture: OPA and AWS CDK rules for HIPAA, FINRA and GxP controls. |
| [llm-devops-remediation-benchmark](https://github.com/SivaSaiKrishnaSuryadevara/llm-devops-remediation-benchmark) | Sanitized CI/CD failure-log dataset and evaluation harness for LLM-driven remediation. |

Supporting repos: [ml-model-pipeline](https://github.com/SivaSaiKrishnaSuryadevara/ml-model-pipeline) (non-LLM failure classifier) ·
[devops-infra-toolkit](https://github.com/SivaSaiKrishnaSuryadevara/devops-infra-toolkit) (Compose, Kubernetes and Terraform for the reference workload)

## Upstream contributions

Fixes I have proposed to the AWS and Kubernetes tooling I use day to day. Each was reproduced and tested before submission.

| Project | Contribution | Status |
| --- | --- | --- |
| [aws/aws-cdk](https://github.com/aws/aws-cdk) | [#39410](https://github.com/aws/aws-cdk/pull/39410): root-caused [#30000](https://github.com/aws/aws-cdk/issues/30000) (Helm `null` values dropped outside TypeScript) to jsii's `any` serialization; documented a verified workaround for the `aws-eks` and `aws-eks-v2` modules | Merged |
| [aws/aws-cdk](https://github.com/aws/aws-cdk) | [#39476](https://github.com/aws/aws-cdk/pull/39476): Amazon Linux 2023 (nodeadm) support for self-managed EKS capacity ([#29983](https://github.com/aws/aws-cdk/issues/29983)), with an integration test deployed on Kubernetes 1.33. [#39411](https://github.com/aws/aws-cdk/pull/39411): documented least-privilege RBAC for ALB Controller OIDC authentication ([#33223](https://github.com/aws/aws-cdk/issues/33223)), verified on a live Kubernetes API server. [#39428](https://github.com/aws/aws-cdk/pull/39428): fixed self-managed EKS nodes on Graviton3/4 instances (`m7g`, `r7g`, `c8g`, `m8g`) getting an x86_64 AMI ([#39427](https://github.com/aws/aws-cdk/issues/39427)) | Open |
| [eksctl-io/eksctl](https://github.com/eksctl-io/eksctl) | [#8907](https://github.com/eksctl-io/eksctl/pull/8907): EFS CSI well-known policy synced with the driver (S3 Files support), with a new policy test; issue [#8906](https://github.com/eksctl-io/eksctl/issues/8906) | Open |
| [awslabs/cdk-eks-blueprints](https://github.com/awslabs/cdk-eks-blueprints) | [#1264](https://github.com/awslabs/cdk-eks-blueprints/pull/1264): EBS and EFS CSI driver IAM policies synced with upstream, with the project's first tests for them | Open |
| [terraform-aws-modules/terraform-aws-iam](https://github.com/terraform-aws-modules/terraform-aws-iam) | [#664](https://github.com/terraform-aws-modules/terraform-aws-iam/pull/664) (EFS CSI S3 Files permissions), [#665](https://github.com/terraform-aws-modules/terraform-aws-iam/pull/665) (missing EBS CSI permissions) | Open |
| [terraform-aws-modules/terraform-aws-eks-pod-identity](https://github.com/terraform-aws-modules/terraform-aws-eks-pod-identity) | [#71](https://github.com/terraform-aws-modules/terraform-aws-eks-pod-identity/pull/71): EFS CSI S3 Files permissions | Open |

## GitHub stats
<picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=SivaSaiKrishnaSuryadevara&show_icons=true&hide=stars&hide_rank=true&theme=dark&disable_animations=true">
    <img alt="Siva's GitHub Stats" src="https://github-readme-stats.vercel.app/api?username=SivaSaiKrishnaSuryadevara&show_icons=true&hide=stars&hide_rank=true&theme=default&disable_animations=true" height="165">
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=SivaSaiKrishnaSuryadevara&layout=compact&theme=dark&disable_animations=true">
  <img alt="Most Used Languages" src="https://github-readme-stats.vercel.app/api/top-langs/?username=SivaSaiKrishnaSuryadevara&layout=compact&theme=default&disable_animations=true" height="165">
</picture>

## Intellectual property

- **Indian patent application 202641038921** (sole inventor), *A System and Method for Predictive CI/CD
  Failure Prevention and Automated Remediation Using Large-Language Models*. Filed 29 Mar 2026,
  published 10 Apr 2026.
- **UK Registered Design 6528756** (co-proprietor), desk-mounted computer display unit for pipeline
  and sales data. Registered 24 May 2026.

## Research

IEEE Senior Member · author of 4+ IEEE Xplore publications on distributed cloud architectures ·
peer reviewer for Elsevier and Springer journals.

## Links

[Website](https://sivasaikrishnasuryadevara.github.io/) ·
[Repo stats dashboard](https://sivasaikrishnasuryadevara.github.io/github-dashboard.html) ·
[Google Scholar](https://scholar.google.com/citations?user=8uy_LdgAAAAJ&hl=en) ·
[LinkedIn](https://linkedin.com/in/sivasaikrishnasuryadevara)
