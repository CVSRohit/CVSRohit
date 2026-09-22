<div align="center">

# Rohit Challa

### AI systems · Security · Computer Vision · Robotics · Product

<p align="center">
<i>I build systems that have to prove they work — models validated against what actually happened,<br/>
robots that refuse to report numbers from unmeasured parameters, and red-team findings<br/>
that ship with the transcript that produced them.</i>
</p>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Rohit_Challa-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rohitchalla)
[![Portfolio](https://img.shields.io/badge/Portfolio-rohitchalla.com-FF0000?style=for-the-badge&logo=google-chrome&logoColor=white)](https://rohitchalla.com)

</div>

---

Most of my work sits where a model meets something that can hurt you if it's wrong — a
vehicle, a production database, a security control, a customer's bill. That constraint
shapes how I build. The through-line across everything below is the same: **the system
carries its own evidence.**

I work across five areas, and the interesting problems keep turning up where they overlap.

---

## AI & Machine Learning

**Applied LLM and agent systems.** Evolutionary prompt optimization with a parallel A/B
testing harness, published to npm. An MCP-compatible memory service with a typed REST API
and pluggable object storage. Natural-language interfaces over structured data. A streaming
rich-text renderer for model output, sanitized by default, published as a React library.
Multi-agent pipelines deployed as containerized APIs, and agent harnesses wired to real
tools rather than demos.

**Knowledge graphs, and learning from absence.** I build *Anti-GraphRAG* — an inversion of
standard graph retrieval that surfaces the edges a graph is *missing* rather than the ones
it already contains. Freeze the graph at time *T*, train ComplEx embeddings, rank absent
edges by significance with a contrastive head, then validate against what actually appeared
after the cutoff: **0.94 P@100** on biomedical data (Hetionet + STRING v12, 47K nodes),
**0.86** on MITRE ATT&CK.

Anything can score candidate edges. Freeze, predict, wait, verify is what separates
significance from noise, and it's the part I care about.

`PyTorch` · `ComplEx / RotatE` · `contrastive learning` · `Claude Agent SDK` · `MCP` · `FastAPI`

---

## Security & AI Red Teaming

I designed and run an AI red team practice covering both directions of the problem — and
they are genuinely different tests:

**Inward — can your own AI be turned against you?** Seven layers, from the model and
provider terms through prompt and context injection, the agent harness, the tool/MCP layer,
RAG and PII boundaries, agent identity and privilege, and governance. Mapped to the OWASP
Top 10 for LLM Applications, the OWASP Top 10 for Agentic Applications, the OWASP MCP Top
10, NIST AI RMF and ISO 42001.

What actually breaks, in practice: unpinned models that silently change behaviour;
payloads hidden in PDFs and tickets an assistant later reads; approval gates that exist but
are trivially satisfied; MCP servers with no auth and no one watching the update path; one
over-permissioned token shared by every agent, with no revocation path.

**Outward — can you survive an attacker using AI against you?** Replicating the AI-enabled
kill chain: automated reconnaissance, synthetic pretexting, adaptive access that rewrites
itself after refusal, agentic lateral movement, targeted extraction. Including the case where
the two sides meet — using an organization's own public-facing assistant as the entry point.
Measured against detection and response, because most environments generate the alert and
nobody reads it.

Every engagement runs on written authorization with named approvers, scoped windows, and
proof-of-compliance stop conditions. Findings ship as an evidence pack — the exact prompt,
transcript or recording that produced each one, reproducible by the client's own team —
mapped to control frameworks so it drops straight into insurer and enterprise
questionnaires.

I hold my own infrastructure to the same standard: deny-by-default row-level security on
every table, a DDL event trigger that auto-enables it on anything created later so the
posture can't drift, `SECURITY DEFINER` functions with pinned `search_path`, and no
data-plane grants to anonymous roles.

`OWASP LLM / Agentic / MCP Top 10` · `NIST AI RMF` · `ISO 42001` · `PIPEDA` · `adversarial simulation`

---

## Computer Vision & Remote Sensing

**Pixels to decisions — from orbit, from a robot, and from a production line.**

Satellite and aerial imagery turned into decision products for environmental
monitoring: fuel-layer characterization, hazard and spread modelling, and risk
surfaces built for the people who have to act on them rather than for a leaderboard.

On the robotics side, LiDAR and camera fused for obstacle detection and range
estimation — with a calibration step that has to run before any range figure is
allowed to mean anything, and evidence-grade logging on every bench run so a
number can always be traced back to the frame it came from. Also inspection and
quality grading on moving production lines, where the constraint is a conveyor
that does not slow down for your inference budget.

`PyTorch` · `OpenCV` · `Satellite & aerial imagery` · `Sensor fusion` · `Object detection` · `Geospatial`

---

## Hardware & Robotics

**Uncrewed ground systems.** Autonomy stack for a tactical cargo UGV — ROS 2 Humble on a
Jetson Orin Nano, 2D LiDAR and camera fused for perception, brushed-motor drivetrain over
an ESP32 controller with a hardware E-stop. A scenario harness runs waypoint following,
obstacle approach, GNSS-denied navigation and link-loss return-to-home across both a
kinematic engine and Gazebo, deterministic given a seed.

The part I'd point at: the harness **refuses to report quotable results while any vehicle
parameter is still a placeholder.** Wheelbase, centre-of-mass and friction coefficients that
haven't been physically measured force a `parameters_measured = false` flag, enforced in
code, not in a comment. Simulation output that can't be traced to a measurement isn't a
result — it's a rendering. Built to a defence innovation challenge's TRL and evidence
requirements.

**Embedded and physical interfaces.** A hardware remote for AI coding agents — ESP32 with a
display and approve/deny buttons, custom firmware, a WebSocket relay, and a 3D-printed
enclosure I modelled in OpenSCAD. It makes the approval step a physical object you have to
reach for, which is a different safety property than a dialog box. Separately, a working
prompt → model → STL → sliced 3MF → printer pipeline, with the firmware quirks documented
so it reproduces on someone else's machine.

`ROS 2` · `Jetson Orin` · `LiDAR + camera fusion` · `ESP32 / PlatformIO` · `Gazebo` · `OpenSCAD` · `C++`

---

## Software & Product

I ship the whole thing, not a notebook. Production Next.js on Vercel; Postgres with
row-level security designed before the first insert; Stripe billing with verified webhooks;
FastAPI services containerized and deployed; object storage, auth, and the boring
operational parts that decide whether any of the above survives contact with users.

Recent builds include a conversational form platform with an embeddable widget and usage
metering, commercial-intelligence tooling over messy source data, and computer-vision
pipelines for environmental monitoring taken from satellite imagery through to a decision
product.

`TypeScript` · `Next.js` · `Python` · `FastAPI` · `PostgreSQL / Supabase` · `Docker` · `Vercel` · `Fly.io` · `GCP` · `AWS`

---

<div align="center">

**Working on knowledge graphs, agent security, or autonomy — and want someone who'll show you the evidence?**

[![Book a Call](https://img.shields.io/badge/Schedule_a_Chat-FF0000?style=for-the-badge)](https://calendly.com/cvsrohit/rohitchalla-com)
[![Portfolio](https://img.shields.io/badge/rohitchalla.com-1A1B27?style=for-the-badge)](https://rohitchalla.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge)](https://linkedin.com/in/rohitchalla)

</div>
