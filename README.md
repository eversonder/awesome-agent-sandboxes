# Awesome agent sandboxes

Places an AI agent can run code, and the tools for building them. A sandbox here means a computer an agent gets for itself: it can run commands, install things and keep files there, away from yours.

Kept by [Eversonder](https://eversonder.com), who read every provider's docs while building [Annex](https://annex.eversonder.com). Corrections and additions are welcome: see [Contributing](#contributing).

## Contents

- [Sandbox providers](#sandbox-providers)
- [Run them yourself](#run-them-yourself)
- [What keeps a sandbox apart](#what-keeps-a-sandbox-apart)
- [One interface over many](#one-interface-over-many)
- [Agents and frameworks that use them](#agents-and-frameworks-that-use-them)
- [Reading](#reading)
- [Contributing](#contributing)

## Sandbox providers

Services that rent you a sandbox by the second or the hour. What each sentence says comes from the provider's own pages; prices, regions and how each one pauses are compared at [annex.eversonder.com/sandbox-prices](https://annex.eversonder.com/sandbox-prices) and [/providers](https://annex.eversonder.com/providers).

| Provider | What it is | A sandbox there is |
|---|---|---|
| [Agent 37](https://www.agent37.com) | Agent 37 runs sandboxes for agents under gVisor, which keeps each one apart from the others. | gVisor sandboxes |
| [AWS](https://aws.amazon.com/ec2/) | Not a sandbox product, but an ordinary EC2 machine in your own account does the job. | EC2 virtual machines |
| [Blaxel](https://blaxel.ai) | Blaxel runs lightweight virtual machines that stand by on their own when nothing is using them. | Lightweight virtual machines |
| [Boat](https://boat.dev) | Boat gives each sandbox a full virtual machine, in Europe. | Full virtual machines |
| [BoxCompute](https://boxcompute.ai) | BoxCompute runs Ubuntu virtual machines in Malaysia. | Ubuntu virtual machines |
| [Buddy](https://buddy.works) | Buddy runs Linux virtual machines as sandboxes, in three parts of the world. | Linux virtual machines |
| [Cloudflare](https://developers.cloudflare.com/containers/) | Cloudflare runs containers on its own network, close to wherever the request came from. | Containers |
| [CreateOS](https://createos.sh) | CreateOS, by NodeOps, runs sandboxes in small virtual machines. | Firecracker virtual machines |
| [Daytona](https://www.daytona.io) | Daytona makes sandboxes built for running code that AI wrote. | Linux sandboxes |
| [Dory](https://dory.run) | Dory gives each sandbox a full Debian virtual machine at a flat price per vCPU. | Full Debian virtual machines |
| [E2B](https://e2b.dev) | E2B makes sandboxes for AI agents, started from templates. | Sandboxes started from templates |
| [Fly.io Sprites](https://sprites.dev) | Sprites are persistent computers from Fly.io that go to sleep by themselves when idle. | Persistent virtual machines |
| [Freestyle](https://www.freestyle.sh) | Freestyle gives agents full virtual machines. | Full virtual machines |
| [InstaBox](https://instabox.sh) | InstaBox runs sandboxes in small virtual machines on Debian. | Firecracker virtual machines |
| [Lizard](https://lizard.build) | Lizard runs sandboxes in small virtual machines in the US and Europe. | Firecracker virtual machines |
| [Maritime](https://maritime.sh) | Maritime sells low-cost sandboxes that work the way E2B's do. | Sandboxes |
| [Mosaic](https://sandbox.mosaicos.com) | Mosaic runs sandboxes in small virtual machines in the United States. | Firecracker virtual machines |
| [Munito](https://munito.ai) | Munito runs sandboxes in small virtual machines, in preview. | Small virtual machines |
| [Namespace](https://namespace.so) | Namespace runs compute instances built for fast builds and tests. | Compute instances |
| [Prized](https://prized.dev) | Prized runs sandboxes in small virtual machines, in beta. | Firecracker virtual machines |
| [Quivvo](https://tryquivvo.com) | Quivvo runs sandboxes in small virtual machines, in Amsterdam and the US. | Firecracker virtual machines |
| [Railway](https://docs.railway.com/sandboxes) | Railway Sandboxes are isolated Linux machines that sit next to the rest of your Railway projects. | Isolated Linux virtual machines |
| [Render](https://render.com/docs/sandboxes) | Render Sandboxes run next to the rest of your Render services, in public beta. | Sandboxes |
| [SuperHQ](https://nanite.run) | SuperHQ runs sandboxes that go quiet by themselves when nothing is using them. | Virtual machines on ARM processors |
| [Superserve](https://superserve.ai) | Superserve runs sandboxes for agents in small virtual machines. | Firecracker virtual machines |
| [Tensorlake](https://tensorlake.ai) | Tensorlake runs sandboxes in small virtual machines. | Small virtual machines |
| [Upstash Box](https://upstash.com/docs/box) | Upstash Box runs containers and bills only for the processor time they use. | Containers |
| [Vercel](https://vercel.com/docs/vercel-sandbox) | Vercel Sandbox runs code in small virtual machines next to the rest of your Vercel projects. | Firecracker virtual machines |
| [Zode](https://zode.dev) | Zode runs sandboxes in small virtual machines in Belgium. | Small virtual machines |
| [Modal](https://modal.com) | Modal runs code in the cloud by the second, with sandboxes among what it offers. | Containers |

## Run them yourself

Open-source projects for running sandboxes on machines you control.

- [E2B](https://github.com/e2b-dev/E2B) - The open-source side of E2B: sandboxes for agents on small virtual machines.
- [Daytona](https://github.com/daytonaio/daytona) - The open-source side of Daytona: sandboxes for running code AI wrote.
- [microsandbox](https://github.com/microsandbox/microsandbox) - Self-hosted sandboxes on small virtual machines.
- [Apple container](https://github.com/apple/container) - Apple's tool for running Linux containers on a Mac, each in a small virtual machine of its own.
- [Annex on your own servers](https://annex.eversonder.com/providers/your-own-servers) - Connect a Mac, a Linux server or a Raspberry Pi and it runs your agents' sandboxes.

## What keeps a sandbox apart

The technology underneath. Nearly every provider above is built on one of these.

- [Firecracker](https://github.com/firecracker-microvm/firecracker) - Small virtual machines that start quickly, written in Rust at AWS. Each sandbox gets a kernel of its own. ([site](https://firecracker-microvm.github.io))
- [Cloud Hypervisor](https://github.com/cloud-hypervisor/cloud-hypervisor) - A virtual machine monitor in Rust for cloud workloads. ([site](https://www.cloudhypervisor.org))
- [gVisor](https://github.com/google/gvisor) - A kernel written for containers, from Google: it sits between the program and the machine's own kernel. ([site](https://gvisor.dev))
- [Kata Containers](https://github.com/kata-containers/kata-containers) - Containers that each run inside a small virtual machine. ([site](https://katacontainers.io))
- [youki](https://github.com/youki-dev/youki) - A container runtime written in Rust.
- [nsjail](https://github.com/google/nsjail) - Walls off a single process with Linux namespaces and system-call filters, from Google.
- [bubblewrap](https://github.com/containers/bubblewrap) - A small tool for sandboxing a process without root, used by Flatpak.

## One interface over many

- [Annex](https://annex.eversonder.com) - One API over the providers above, on your own accounts: it picks the cheapest, fastest or a named one, moves on when one is full, and can pause a sandbox or move a task between machines. ([command](https://github.com/eversonder/annex-cli), [examples](https://github.com/eversonder/annex-examples), [templates](https://github.com/eversonder/annex-templates))
- [ComputeSDK](https://github.com/computesdk/computesdk) - An open-source library with one interface over several sandbox providers.

## Agents and frameworks that use them

- [Claude Code](https://github.com/anthropics/claude-code) - Anthropic's coding agent for the terminal. ([docs](https://code.claude.com/docs))
- [Codex](https://github.com/openai/codex) - OpenAI's coding agent for the terminal.
- [Cursor](https://cursor.com) - An editor with a coding agent built in.
- [Claude Agent SDK](https://code.claude.com/docs/en/agent-sdk) - Build your own agents on what Claude Code is built on.
- [OpenAI Agents SDK](https://openai.github.io/openai-agents-python/) - OpenAI's library for building agents.
- [AI SDK](https://ai-sdk.dev) - Vercel's TypeScript library for building with models and tools.
- [LangChain](https://www.langchain.com) - A framework for building agents and the applications around them.
- [Model Context Protocol](https://modelcontextprotocol.io) - The open protocol many agents use to reach tools, sandboxes among them.

## Reading

- [What is a sandbox for an AI agent?](https://annex.eversonder.com/guides/what-is-an-agent-sandbox) - The plain explanation.
- [How to choose a sandbox provider](https://annex.eversonder.com/guides/choosing-a-sandbox-provider) - What actually differs between them.
- [Sandboxes in Europe](https://annex.eversonder.com/guides/sandboxes-in-europe) - Which providers run there.
- [Twelve things to build with a sandbox](https://annex.eversonder.com/use-cases) - Six with a full walkthrough and code.
- [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) - Anthropic on when an agent is the right tool, and how to keep one simple.

## Contributing

Open a pull request. A new entry needs a link, one plain sentence saying what the thing is, and a source for anything it claims. Providers are listed alphabetically and described in their own terms.

Two things this list does not carry: start-up times or other speed comparisons (several providers' terms forbid publishing them, and the numbers go stale within weeks), and anything that can't be traced to a page you can read.

## Licence

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/): do what you like with it.
