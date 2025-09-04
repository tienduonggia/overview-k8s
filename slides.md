---
# config for the whole slides and the first one

addons:
  - slidev-addon-python-runner
  - slidev-addon-rabbit
rabbit:
  slideNum: true   # Show current/total slide numbers next to a rabbit icon

theme: bricks

# some information about your slides (markdown enabled)
title: Overview Kubernetes (K8s)
exportFilename: Overview Kubernetes 2025-09
author: Roy Yang
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false

# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: fade-out

# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true

# show line numbers in code blocks
lineNumbers: True
glowSeed: 229
# controls whether texts in slides are selectable
selectable: true
---

# Overview Kubernetes

Research • Share • Learn Together

 

---
src: ./pages/toc.md
---

---
src: ./pages/scale.md
---

---
src: ./pages/docker.md
---

---
src: ./pages/k8s.md
---

---
src: ./pages/k8s-cluster.md
---

---
src: ./pages/pod.md
---

---
src: ./pages/controller.md
---

---
src: ./pages/deployment.md
---

---
src: ./pages/service.md
---

---
src: ./pages/volume.md
---

