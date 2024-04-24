<a href="https://reporacers.com/" taarget="_blank">
  <img src="https://github.com/repo-racers/.github/blob/main/profile/repo-racers.svg" alt="Repo Raacers" width="600px"/>
</a>

This repository is included in our open-source Pro Support service which offers an efficient solution for managing popular GitHub Actions dependencies with ease:

🙌 forked from [diggerhq/digger](https://github.com/diggerhq/digger)

<details>

<summary>What is Open-Source Pro Support?</summary>

Open-Source Pro Support is a comprehensive service designed to streamline your workflow by providing:

- **Customized Forks:** We create public forks of popular GitHub Actions, ensuring you have access to the latest features and fixes.
  
- **Dedicated Technical Support:** Say goodbye to the hassle of managing multiple open-source dependencies. With our service, you have a single point of contact for all your support needs. Reach out to us on our [Discord](https://discord.com/channels/1229786735161118882/1229786735161118885) server, and our team of experts will be ready to assist you.
  
- **Priority Fixes:** Experience seamless issue resolution with our priority fix service. If you encounter any issues with our forks, we prioritize fixing them promptly to minimize disruptions to your workflow.
  
- **Community Contribution:** We believe in giving back to the open-source community. When we fix issues in our forks, we handle creating pull requests to the original authors, ensuring that the entire community benefits from the improvements.

</details>

<details>

<summary>How It Works</summary>


1. **Choose Our Fork:** Instead of referencing popular GitHub Actions repositories directly, simply reference this repository in your workflow.
   
2. **Enjoy Dedicated Support:** If you encounter any issues or need assistance, reach out to us on our [Discord](https://discord.com/channels/1229786735161118882/1229786735161118885) server. Our team will be happy to help you promptly.
   
3. **Benefit from Priority Fixes:** Experience seamless issue resolution with our priority fix service. We prioritize fixing issues in our forks to ensure smooth operation for your projects.
   
4. **Contribute to the Community:** Rest assured that when we fix issues in our forks, we contribute back to the original repositories, benefiting the entire open-source community.

*Not Your Thing?*

We don't want to get in between you and the community. If you want to handle forking and submitting a pull request yourself, that's awesome.

However, feel free to reach out to us on [Discord](https://discord.com/channels/1229786735161118882/1229786735161118885) anyway if you need any help and advice in doing so.

:heart: [open-source](https://opensource.org/)

</details>

---

CI/CD for Terraform is [tricky](https://itnext.io/pains-in-terraform-collaboration-249a56b4534e). To make life easier, specialised CI systems aka [TACOS](https://itnext.io/spice-up-your-infrastructure-as-code-with-tacos-1a9c179e0783) exist - Terraform Cloud, Spacelift, Atlantis, etc.

But why have 2 CI systems? Why not reuse the async jobs infrastructure with compute, orchestration, logs, etc of your existing CI?

Digger runs terraform natively in your CI. This is:

- Secure, because cloud access secrets aren't shared with a third-party
- Cost-effective, because you are not paying for additional compute just to run your terraform

## Features

- Terraform plan and apply in pull request comments
- Private runners - thanks to the fact that there are no separate runners! Your existing CI's compute environment is used
- Open Policy Agent (OPA) support for RBAC
- PR-level locks (on top of Terraform native state locks, similar to Atlantis) to avoid race conditions across multiple PRs
- Terragrunt, Workspaces, multiple Terraform versions, static analysis via Checkov, plan persistence, ...
- Drift detection 
  

## Getting Started

- [Github Actions + AWS](https://docs.digger.dev/getting-started/github-actions-+-aws)
- [Github Actions + GCP](https://docs.digger.dev/getting-started/github-actions-and-gcp)

## How it works

Digger has 2 main components:
- CLI that runs inside your CI and calls terraform with the right arguments
- Orchestrator - a minimal backend (that can also be self-hosted) that triggers CI jobs in response to events such as PR comments

Digger also stores PR-level locks and plan cache in your cloud account (DynamoDB + S3 on AWS, equivalents in other cloud providers)

## Contributing

We love contributions. Check out our [contributing guide](CONTRIBUTING.md) to get started.

Not sure where to get started? You can:

-   [Book a free, non-pressure pairing session / code walkthrough with one of our teammates](https://calendly.com/diggerdev/digger-pro-demo-clone)!
-   Join our <a href="https://join.slack.com/t/diggertalk/shared_invite/zt-1tocl4w0x-E3RkpPiK7zQkehl8O78g8Q">Slack</a>, and ask us any questions there.

## Telemetry

Digger collects anonymized telemetry. See [usage.go](https://github.com/diggerhq/digger/blob/develop/cli/pkg/usage/usage.go) for detail. You can disable telemetry collection either by setting `telemetry: false` in digger.yml, or by setting the `TELEMETRY` env variable to `false`.

## Running migrations

```
atlas migrate apply --url $DATABASE_URL
```

## Resources

- [Docs](https://docs.digger.dev/) for comprehensive documentation and guides
- [Slack](https://join.slack.com/t/diggertalk/shared_invite/zt-1tocl4w0x-E3RkpPiK7zQkehl8O78g8Q) for discussion with the community and Digger team.
- [GitHub](https://github.com/diggerhq/digger) for code, issues, and pull request
- [Medium](https://medium.com/@DiggerHQ) for terraform automation and collaboration insights, articles, tutorials, and updates.

---

> [!TIP]
> For support with this repo and many other open-source projects, visit us at https://reporacers.com/ and join us on  [Discord](https://discord.com/channels/1229786735161118882/1229786735161118885).
