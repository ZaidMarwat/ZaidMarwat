<img src="assets/terminal.svg" alt="Terminal: whoami — Zaid Marwat, CS at UT Austin, graduating May 2027. Focus: virtualization, distributed systems, the layer underneath. Proof: US patent US20240085134A1, Podman PR 27778, a published journal article." width="100%">

<p>
  <a href="https://zaidmarwat.com"><img alt="site" src="https://img.shields.io/badge/site-zaidmarwat.pages.dev-fe8019?style=flat-square&labelColor=282828"></a>
  <a href="mailto:zaidratify123@gmail.com"><img alt="email" src="https://img.shields.io/badge/email-zaidratify123-b8bb26?style=flat-square&labelColor=282828"></a>
  <a href="https://patents.google.com/patent/US20240085134A1/en"><img alt="patent" src="https://img.shields.io/badge/US%20patent-US20240085134A1-d3869b?style=flat-square&labelColor=282828"></a>
  <img alt="grad" src="https://img.shields.io/badge/graduating-May%202027-83a598?style=flat-square&labelColor=282828">
</p>

<p>
  <img alt="Go" src="https://img.shields.io/badge/Go-8ec07c?style=flat-square&logo=go&logoColor=282828">
  <img alt="Python" src="https://img.shields.io/badge/Python-fabd2f?style=flat-square&logo=python&logoColor=282828">
  <img alt="C" src="https://img.shields.io/badge/C-83a598?style=flat-square&logo=c&logoColor=282828">
  <img alt="C++" src="https://img.shields.io/badge/C++-83a598?style=flat-square&logo=cplusplus&logoColor=282828">
  <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-83a598?style=flat-square&logo=typescript&logoColor=282828">
  <img alt="Linux" src="https://img.shields.io/badge/Linux-fe8019?style=flat-square&logo=linux&logoColor=282828">
  <img alt="Docker" src="https://img.shields.io/badge/Docker-8ec07c?style=flat-square&logo=docker&logoColor=282828">
  <img alt="Kubernetes" src="https://img.shields.io/badge/Kubernetes-8ec07c?style=flat-square&logo=kubernetes&logoColor=282828">
  <img alt="SQLite" src="https://img.shields.io/badge/SQLite-d3869b?style=flat-square&logo=sqlite&logoColor=282828">
  <img alt="Neovim" src="https://img.shields.io/badge/Neovim-b8bb26?style=flat-square&logo=neovim&logoColor=282828">
</p>

---

### The through-line

The first program I wrote saved the last command's output into a variable called `$L` so I
could hand it to the next one. It was not elegant. The habit stuck: when a system makes me
do something tedious twice, I go build the thing that does it for me.

```mermaid
%%{init: {'theme':'base','themeVariables':{
  'primaryColor':'#3c3836','primaryTextColor':'#ebdbb2','primaryBorderColor':'#fe8019',
  'lineColor':'#928374','fontFamily':'ui-monospace, monospace','fontSize':'14px'}}}%%
flowchart LR
    A["<b>$L</b><br/>first script"] --> B["<b>AutoShell</b><br/>extended in C"]
    B --> C["<b>fab automation</b><br/>85–90% of workflows"]
    C --> D["<b>test hub</b><br/>schema + indexes"]
    D --> E["<b>Podman</b><br/>ancestor filter fix"]
    style A fill:#504945,stroke:#fe8019,color:#ebdbb2
    style E fill:#504945,stroke:#b8bb26,color:#ebdbb2
```

Different scales, same instinct: make the layer underneath more trustworthy so the people
standing on it can move faster.

---

### Selected work

<details open>
<summary><b>🔧 Podman #27778</b> — fix the <code>ancestor</code> filter to resolve image names to IDs <em>(open)</em></summary>

<br/>

Image names are **mutable** — a tag can point at a different image tomorrow. Image IDs are
not. The `--filter ancestor=` path was comparing against the name, so a container could be
matched to the wrong ancestor once a tag moved.

```go
// pkg/domain/filters/containers.go   +43 −35
// resolve the supplied name to an immutable ID before comparing
```

Closes [#27743](https://github.com/podman-container-tools/podman/issues/27743) ·
[read the PR →](https://github.com/podman-container-tools/podman/pull/27778)

</details>

<details>
<summary><b>📜 U.S. Patent US20240085134A1</b> — thermal-imaging friendly-fire avoidance</summary>

<br/>

Real-time detection of human silhouettes in live infrared feeds. The hard part was never
detection — it was detection *fast enough to matter*. In a safety system, a correct answer
that arrives late is worse than useless, so most of the work was profiling the pipeline end
to end and optimising the hot path.

`Python` · `OpenCV` · `Embedded Linux` ·
[read the patent →](https://patents.google.com/patent/US20240085134A1/en)

</details>

<details>
<summary><b>🧠 Brain-Computer Interface Wheelchair</b> — published research, featured on CBS</summary>

<br/>

A close friend's grandfather was losing the ability to walk, so a few of us built a BCI
wheelchair prototype in his honour: a real-time EEG pipeline in C++ and Python on a
Raspberry Pi, turning noisy sensor data into movement, with ML classification tuned for
real-world noise.

Presented at the Advancing Healthcare Innovation Summit, featured on CBS, and published in
the *Journal of Innovation in Digital Health, Diagnostics, and Biomarkers*.

It is the one I am proudest of, because it started with somebody specific rather than a spec.

</details>

<details>
<summary><b>⌨️ tsk</b> — a task manager that lives in your terminal</summary>

<br/>

SQLite-backed, zero dependencies, 59 tests. Built because the alternative was another
Electron app.

```
$ tsk list
  5 [ ]! Email recruiter          4d ago    +jobhunt
  1 [ ]! Fix ancestor filter      tomorrow  +podman  @go @oss
  2 [ ]  Push profile README      today     +jobhunt
```

`--json` on every command, so it pipes into `jq`. Exit codes are part of the contract.
One index, shaped for the only query that runs constantly.

[browse the code →](https://github.com/ZaidMarwat/tsk)

</details>

---

### Where I've worked

| | | |
|---|---|---|
| **Visa** | Software Engineer Intern | May–Aug 2026 |
| **Texas Instruments** | Software Engineer Intern | May–Aug 2025 |

<details>
<summary>what I actually did</summary>

<br/>

**Visa** — Backend services and test infrastructure over high-volume transaction data in
live payment systems. Built the internal test hub and owned the schema and indexing
decisions behind it. Dashboards, logging pipelines, A/B tests, and on-call.

**Texas Instruments** — Automated 85–90% of fab simulation workflows across distributed
Linux compute. Extended the internal shell scripting language (written in C) that drives
them. Error handling and job recovery that saved 150+ machine hours a quarter. Carried
on-call for job failures and wrote the runbooks other engineers worked from.

</details>

---

### Away from a terminal

Self-taught piano from those YouTube videos with the falling notes, practising at night in
an empty dorm room. Mostly anime soundtracks — *Hikaru Nara* took the longest and is still
my favourite. Officer of my university's fragrance club, which sounds like a non sequitur
until you notice a scent is a system too: layered, rule-bound, and quietly shaped by
everyone around the person who chose it. Currently deep in Sanderson's *Stormlight Archive*.

<sub>nvim, unreasonably. 📫 <a href="mailto:zaidratify123@gmail.com">zaidratify123@gmail.com</a></sub>
