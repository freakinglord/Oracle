---
title: LXC vs Docker vs Kubernetes vs VMs
tags: [containers, lxc, docker, kubernetes, virtualization, technology-radar]
source: query
source_type: query
created: 2026-08-04
updated: 2026-08-04 18:29
---

# LXC vs Docker vs Kubernetes vs VMs

## Overview
LXC, Docker, Kubernetes, and VMs sit at different layers of the
isolation/virtualization stack — LXC and Docker are both OS-level
virtualization (share the host kernel) but differ in what they're optimized
to package; Kubernetes is an orchestrator, not a runtime; VMs virtualize
hardware, not just the OS.

## Key Points
- **LXC** = OS-level virtualization using Linux kernel primitives directly
  (cgroups for resource limits, namespaces for PID/net/mount/user/UTS/IPC
  isolation, chroot/pivot_root for filesystem isolation). Produces a "system
  container": boots an init system, runs multiple processes/services, feels
  like a lightweight VM rather than a single app.
- **Docker** uses the same underlying kernel mechanisms (and historically
  used LXC itself in early versions) but is optimized around the
  "application container" convention: one process/service per container,
  images built in layers via a Dockerfile, distributed through registries
  (Docker Hub). The differentiator is ecosystem and workflow (Compose,
  build tooling), not the isolation primitives.
- **Kubernetes** is not a container runtime — it's an orchestrator. It
  schedules, scales, network-connects, and heals containers (produced by
  Docker/containerd/CRI-O via the OCI/CRI interfaces) across a cluster.
  Comparing it to LXC/Docker is a category error: it's "fleet management,"
  not "how is isolation achieved." Kubernetes' CRI is built around
  OCI-style app containers, not LXC's system-container model, so "LXC on
  Kubernetes" isn't part of the mainstream workflow.
- **VMs** virtualize hardware, not the OS: each VM runs its own kernel via a
  hypervisor (KVM, Hyper-V, ESXi). Strongest isolation boundary of the four
  (a kernel exploit in one VM can't reach another the way it can across
  containers sharing a host kernel), but heaviest — own kernel, memory
  duplication, slower boot.
- Overhead/isolation ordering: VMs (heaviest, strongest isolation) > LXC ≈
  Docker (shared kernel, lightweight, weaker isolation boundary) — LXC and
  Docker have essentially the same overhead profile since both rely on the
  same kernel features.

## Details

### Where LXC and Docker actually diverge
Both are namespaces+cgroups under the hood. The real difference is
intent and convention:

| | LXC | Docker |
|---|---|---|
| Unit of abstraction | A machine (system container) | An application (app container) |
| Typical contents | Full init system, multiple services | One process/service (by convention) |
| Image model | OS templates, thinner layering story | Layered images, Dockerfile, registries |
| Ecosystem | Minimal — mostly just the runtime | Huge — Compose, Hub, build tooling |
| Orchestration tooling | Manual | Native fit with Kubernetes/Swarm |

### Technology Radar-style assessment (author's own, not ThoughtWorks')
Framed using the ring methodology from
[ThoughtWorks Technology Radar Vol 34](../../technology-radar/wiki/thoughtworks-technology-radar-vol-34.md)
(Adopt / Trial / Assess / Caution) — applied here to the four technologies
themselves, not to a specific tool release.

- **Docker (app containers) — Adopt.** Ubiquitous, mature, default choice
  for packaging an application and its dependencies. The ecosystem
  (registries, Compose, broad CI/CD integration) is the deciding factor over
  raw LXC, not the isolation mechanism itself.
- **Kubernetes — Adopt** for organizations running multiple services at real
  scale or needing self-healing/auto-scaling; **Caution** for a single app
  or a small team — the operational complexity (etcd, control plane,
  networking/CNI, RBAC) is a poor trade for workloads that don't need fleet
  orchestration. Don't adopt Kubernetes to get Docker's benefits; adopt it
  when you have a fleet problem.
- **LXC (system containers) — Assess.** Technically solid and still actively
  used (Proxmox, Incus/LXD, some cloud-native sandboxing use cases wanting a
  persistent "VM-like" container), but it's a narrower niche today: most
  teams that want app packaging reach for Docker (bigger ecosystem), and
  most teams that want a full isolated machine reach for a VM (stronger
  isolation, no shared-kernel risk). Worth knowing about for the specific
  case of wanting VM-like persistence/multi-process behavior without
  hypervisor overhead — not a default recommendation over the other three.
- **VMs — Adopt.** Still foundational wherever the isolation boundary
  matters most (multi-tenant hosting, strict compliance/security
  boundaries, running a different kernel/OS than the host, legacy/stateful
  workloads). Not being displaced by containers — the two are complementary
  layers (containers commonly run *inside* VMs in cloud environments) rather
  than competitors for the same job.

## Related
- [ThoughtWorks Technology Radar Vol 34](../../technology-radar/wiki/thoughtworks-technology-radar-vol-34.md) — source of the Adopt/Trial/Assess/Caution ring methodology applied above.

## Open questions / gaps
This page is general-knowledge synthesis, not sourced from an ingested
document — flagging per the wiki's no-fabrication rule. If a specific
source (vendor docs, a Radar edition that actually blips one of these four,
a benchmark) gets ingested later, reconcile it against the assessment above
rather than assuming this page is authoritative.
