# Hi, I'm Siva Sai Krishna Suryadevara

**Senior Cloud Platform & DevOps Architect @ Evinova (AstraZeneca) · IEEE Senior Member**

I work on container security and safe automation: giving AI agents guarded access to Docker,
hardening Compose and rootless Docker setups, and CI pipelines that diagnose their own build
failures. I write about it on HackerNoon and contribute fixes upstream to the AWS and Kubernetes
tooling I use every day.

## Docker projects

| Repository | What it does |
| --- | --- |
| [docker-mcp-guardian](https://github.com/SivaSaiKrishnaSuryadevara/docker-mcp-guardian) | MCP server that gives Claude and other agents read-mostly access to Docker: read-only by default, deny-listed restarts resolved by canonical name, secrets redacted, rootless socket preferred and fail-closed. |
| [docker-ci-gatekeeper](https://github.com/SivaSaiKrishnaSuryadevara/docker-ci-gatekeeper) | Self-healing Docker CI step: parses BuildKit failures into a typed taxonomy, asks Claude Code for a minimal fix, verifies it with a rebuild. Hard cap of 2 attempts; fixes are staged, never applied blind. |
| [docker-multiarch-builder](https://github.com/SivaSaiKrishnaSuryadevara/docker-multiarch-builder) | Benchmark of QEMU emulation vs native Buildx nodes for multi-arch images. Measured: emulated arm64 builds ran ~16x slower; emulated amd64 on ARM crashed or hung in 5 of 5 runs. Raw data included. |

## Writing

| Article | Published |
| --- | --- |
| [Don't Hand Claude Your Docker Socket: Build It a Guarded One](https://hackernoon.com/dont-hand-claude-your-docker-socket-build-it-a-guarded-one) | HackerNoon, Oct 21, 2026 |
| [Hardening Production Multi-Container Topologies with Docker Compose v2](https://hackernoon.com/hardening-production-multi-container-topologies-with-docker-compose-v2) | HackerNoon, Nov 5, 2026 |
| [Taming Autonomous AI Agents with Rootless Docker](https://hackernoon.com/taming-autonomous-ai-agents-with-rootless-docker) | HackerNoon, Nov 6, 2026 |

## Other projects

| Repository | What it does |
| --- | --- |
| [predictive-cicd-remediation](https://github.com/SivaSaiKrishnaSuryadevara/predictive-cicd-remediation) | Prototype of the system in my Indian patent application 202641038921: LLM-based prediction and automated remediation of CI/CD failures. |
| [zero-trust-cloud-governance-pac](https://github.com/SivaSaiKrishnaSuryadevara/zero-trust-cloud-governance-pac) | Reference policy-as-code architecture: OPA and AWS CDK rules for HIPAA, FINRA and GxP controls. |
| [llm-devops-remediation-benchmark](https://github.com/SivaSaiKrishnaSuryadevara/llm-devops-remediation-benchmark) | Sanitized CI/CD failure-log dataset and evaluation harness for LLM-driven remediation. |

Supporting repos: [ml-model-pipeline](https://github.com/SivaSaiKrishnaSuryadevara/ml-model-pipeline) (non-LLM failure classifier) ·
[devops-infra-toolkit](https://github.com/SivaSaiKrishnaSuryadevara/devops-infra-toolkit) (Compose, Kubernetes and Terraform for the reference workload)

## Upstream contributions

Fixes to the AWS and Kubernetes tooling I use day to day. Most come from one finding: infrastructure-as-code modules ship hand-copied IAM policies for Kubernetes storage and load-balancer drivers, and those copies drift out of sync with the drivers' upstream policies.

### Merged

| Project | Contribution | Merged | Released in |
| --- | --- | --- | --- |
| [aws/aws-cdk](https://github.com/aws/aws-cdk) | [#39428](https://github.com/aws/aws-cdk/pull/39428): fixed self-managed EKS nodes on Graviton3/4 instances (`m7g`, `r7g`, `c8g`, `m8g`) getting an x86_64 AMI ([#39427](https://github.com/aws/aws-cdk/issues/39427)) | Nov 9, 2026 | [v2.276.0](https://github.com/aws/aws-cdk/releases/tag/v2.276.0) |
| [aws/aws-cdk](https://github.com/aws/aws-cdk) | [#39411](https://github.com/aws/aws-cdk/pull/39411): documented least-privilege RBAC for ALB Controller OIDC authentication ([#33223](https://github.com/aws/aws-cdk/issues/33223)) | Nov 2, 2026 | [v2.276.0](https://github.com/aws/aws-cdk/releases/tag/v2.276.0) |
| [aws/aws-cdk](https://github.com/aws/aws-cdk) | [#39410](https://github.com/aws/aws-cdk/pull/39410): root-caused [#30000](https://github.com/aws/aws-cdk/issues/30000) (Helm `null` values dropped outside TypeScript) and documented a verified workaround | Oct 25, 2026 | [v2.275.0](https://github.com/aws/aws-cdk/releases/tag/v2.275.0) |
| [terraform-aws-modules/terraform-aws-iam](https://github.com/terraform-aws-modules/terraform-aws-iam) | [#665](https://github.com/terraform-aws-modules/terraform-aws-iam/pull/665): missing EBS CSI driver permissions | Nov 16, 2026 | [v6.10.0](https://github.com/terraform-aws-modules/terraform-aws-iam/releases/tag/v6.10.0) |
| [terraform-aws-modules/terraform-aws-iam](https://github.com/terraform-aws-modules/terraform-aws-iam) | [#664](https://github.com/terraform-aws-modules/terraform-aws-iam/pull/664): EFS CSI S3 Files permissions | Nov 16, 2026 | [v6.11.0](https://github.com/terraform-aws-modules/terraform-aws-iam/releases/tag/v6.11.0) |
| [terraform-aws-modules/terraform-aws-eks-pod-identity](https://github.com/terraform-aws-modules/terraform-aws-eks-pod-identity) | [#71](https://github.com/terraform-aws-modules/terraform-aws-eks-pod-identity/pull/71): EFS CSI S3 Files permissions | Nov 16, 2026 | [v2.11.0](https://github.com/terraform-aws-modules/terraform-aws-eks-pod-identity/releases/tag/v2.11.0) |

### In review

| Project | Contribution |
| --- | --- |
| [aws/aws-cdk](https://github.com/aws/aws-cdk) | [#39697](https://github.com/aws/aws-cdk/pull/39697): Fargate profile deletion fails after CloudFormation cancels its creation ([#32909](https://github.com/aws/aws-cdk/issues/32909)) |
| [aws/aws-cdk](https://github.com/aws/aws-cdk) | [#39675](https://github.com/aws/aws-cdk/pull/39675): Windows nodegroup roles missing the `eks:kube-proxy-windows` group in aws-auth ([#36625](https://github.com/aws/aws-cdk/issues/36625)) |
| [aws/aws-cdk](https://github.com/aws/aws-cdk) | [#39476](https://github.com/aws/aws-cdk/pull/39476): Amazon Linux 2023 (nodeadm) support for self-managed EKS capacity ([#29983](https://github.com/aws/aws-cdk/issues/29983)), with an integration test deployed on Kubernetes 1.33 |
| [eksctl-io/eksctl](https://github.com/eksctl-io/eksctl) | [#8907](https://github.com/eksctl-io/eksctl/pull/8907): EFS CSI well-known policy synced with the driver, with a new policy test ([#8906](https://github.com/eksctl-io/eksctl/issues/8906)) |
| [terraform-aws-modules/terraform-aws-eks-pod-identity](https://github.com/terraform-aws-modules/terraform-aws-eks-pod-identity) | [#75](https://github.com/terraform-aws-modules/terraform-aws-eks-pod-identity/pull/75): EBS CSI policy resources scoped to match the upstream driver policy (`CreateSnapshot` was granted on `*` without a condition) |
| [awslabs/cdk-eks-blueprints](https://github.com/awslabs/cdk-eks-blueprints) | [#1264](https://github.com/awslabs/cdk-eks-blueprints/pull/1264): EBS and EFS CSI driver IAM policies synced with upstream, with the project's first tests for them |

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

IEEE Senior Member · 5 IEEE conference papers · peer reviewer for Elsevier and Springer Nature journals ·
talk proposal on IAM policy drift in infrastructure-as-code submitted to ChainSEC 2027 (ICSE workshop, under review)

## Links

[Website](https://sivasaikrishnasuryadevara.github.io/) ·
[LinkedIn](https://linkedin.com/in/sivasaikrishnasuryadevara)
