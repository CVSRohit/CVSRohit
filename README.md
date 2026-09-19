<div align="center">

# Rohit Challa

### AI systems · Security · Robotics · Product

<p align="center">
<i>I build systems that have to prove they work — models validated against what actually happened,<br/>
robots that refuse to report numbers from unmeasured parameters, and red-team findings<br/>
that ship with the transcript that produced them.</i>
</p>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Rohit_Challa-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rohitchalla)
[![Portfolio](https://img.shields.io/badge/Portfolio-rohitchalla.com-3B82F6?style=for-the-badge&logo=google-chrome&logoColor=white)](https://rohitchalla.com)

</div>

---

Most of my work sits where a model meets something that can hurt you if it's wrong — a
vehicle, a production database, a security control, a customer's bill. That constraint
shapes how I build. The through-line across everything below is the same: **the system
carries its own evidence.**

I work across four areas, and the interesting problems keep turning up where they overlap.

---

## 🧠 AI & Machine Learning

**Knowledge graph embeddings and learning from absence.** I work on *Anti-GraphRAG* — an
inversion of standard graph retrieval that surfaces the edges a knowledge graph is
*missing* rather than the ones it contains. A missing protein interaction, an undocumented
adversary technique, an unlinked regulatory obligation: meaningful absence often carries
more signal than presence.

The method: freeze a domain graph at time *T*, train ComplEx embeddings on it, then apply a
contrastive head (InfoNCE over frozen embeddings) that ranks absent edges by *significance*
rather than mere likelihood — and validate by checking which predicted voids were confirmed
by real-world data published after the cutoff.

| Domain | Graph | Validated against | P@100 |
|---|---|---|---|
| Biomedical | Hetionet + STRING v12 · 47K nodes, 2.25M edges | Interactions added post-cutoff | **0.94** |
| Threat intelligence | MITRE ATT&CK Enterprise · 1,757 nodes, 20K edges | ATT&CK edges added post-cutoff | **0.86** |

Anything can score candidate edges. Freeze → predict → wait → verify is what separates
significance from noise, and it's the part I care about.

**Applied LLM and agent systems.** Evolutionary prompt optimization with a parallel A/B
testing harness (published to npm). An MCP-compatible memory service with a typed REST API
and pluggable object storage. Natural-language interfaces over structured data. A streaming
rich-text renderer for model output, sanitized by default, published as a React library.
Multi-agent pipelines deployed as containerized APIs.

`PyTorch` · `ComplEx / RotatE` · `contrastive learning` · `Claude Agent SDK` · `MCP` · `FastAPI`

---

## 🛡️ Security & AI Red Teaming

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
itself after refusal, agentic lateral movement, targeted extraction. Including the crossover
case clients remember — using their own public-facing assistant as the initial access vector.
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

## 🔧 Hardware & Robotics

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

## 💻 Software & Product

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

[![Book a Call](https://img.shields.io/badge/📅_Schedule_a_Chat-3B82F6?style=for-the-badge)](https://calendly.com/cvsrohit/rohitchalla-com)
[![Portfolio](https://img.shields.io/badge/🌐_rohitchalla.com-1A1B27?style=for-the-badge)](https://rohitchalla.com)
[![LinkedIn](https://img.shields.io/badge/💼_LinkedIn-0077B5?style=for-the-badge)](https://linkedin.com/in/rohitchalla)

</div>
