## Zaid Marwat

CS at UT Austin, graduating May 2027. I build and repair the layer other people stand on:
automation, tooling, and infrastructure that stays out of the way when it works.

```
zaid@utaustin
─────────────────────────────────────────────
  Host       The University of Texas at Austin
  Kernel     Computer Science BS · GPA 3.86
  Uptime     graduating May 2027
  Shell      bash · zsh
  Editor     nvim
  Languages  Go · Python · C · C++ · TypeScript
  Focus      virtualization · distributed systems · infrastructure
  Patent     US20240085134A1
```

### What I actually do

The first program I wrote saved the last terminal command's output into a variable called
`$L` so I could hand it to the next one. It was not elegant, but the habit stuck: when a
system makes me do something tedious twice, I go build the thing that does it for me.

That is most of what follows. A shell language extended in C so other engineers could drive
simulations. Automation that absorbed 85–90% of a semiconductor fab's simulation workflows.
A test hub with the schema and indexing decisions underneath it. A filter bug in an
open-source container engine.

### Selected work

**[Podman #27778](https://github.com/podman-container-tools/podman/pull/27778)** — Fix the
`ancestor` filter to resolve image names to IDs *(open)*
Image names are mutable and can point to different images over time; image IDs are not. The
filter was comparing against the mutable name, so containers could be matched to the wrong
ancestor. Go, in `pkg/domain/filters/containers.go`.

**[U.S. Patent US20240085134A1](https://patents.google.com/patent/US20240085134A1/en)** —
Thermal-imaging friendly-fire avoidance system
Real-time detection of human silhouettes in live infrared feeds. The hard part was never
detection, it was detection fast enough to matter: in a safety system, a correct answer that
arrives late is worse than useless.

**Brain-Computer Interface Wheelchair** — published research
A close friend's grandfather was losing the ability to walk, so a few of us built a BCI
wheelchair prototype in his honour: a real-time EEG pipeline in C++ and Python on a Raspberry
Pi, turning noisy sensor data into movement. Presented at the Advancing Healthcare Innovation
Summit, featured on CBS, and published in the *Journal of Innovation in Digital Health,
Diagnostics, and Biomarkers*.

**[zaidmarwat.pages.dev](https://zaidmarwat.pages.dev)** — personal site
Runs a working shell in the browser. It implements `$L`.

### Experience

**Visa** · Software Engineer Intern · May–Aug 2026
Backend services and test infrastructure over high-volume transaction data in live payment
systems. Dashboards, logging pipelines, and on-call.

**Texas Instruments** · Software Engineer Intern · May–Aug 2025
Fab simulation automation across distributed Linux compute. Extended the internal shell
language (C), built job recovery that saved 150+ machine hours/quarter, carried on-call.

### Elsewhere

nvim, unreasonably. Self-taught piano, mostly anime soundtracks, *Hikaru Nara* took the
longest. Officer of my university's fragrance club, which sounds like a non sequitur until
you notice a scent is a system too. Currently deep in Sanderson's *Stormlight Archive*.

📫 zaidratify123@gmail.com
