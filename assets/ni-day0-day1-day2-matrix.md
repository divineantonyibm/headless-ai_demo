# Day 0 / Day 1 / Day 2 Use-Case Matrix
## IBM Network Intelligence as the Brain — Network Lifecycle Orchestration

**Lifecycle Framing:**
- **Day 0 — Design & Planning:** Capacity planning, topology design, baseline modeling, DNS architecture, SLA definition
- **Day 1 — Deployment & Provisioning:** Device onboarding, DNS record provisioning, traffic policy activation, monitoring baseline setup, first-alert tuning
- **Day 2 — Operations & Optimization:** Anomaly detection, root-cause analysis, autonomous remediation, traffic re-routing, performance optimization, cost right-sizing, incident management, post-incident learning

**Status Key:**
- ✅ Confirmed — integration mechanism documented
- 🔶 Architectural — supported by mechanisms, not yet a named product integration
- 🔮 Future — capability gap, logical next step

---

## DAY 0 — Design & Planning

NI's role on Day 0: **Analytical intelligence layer** — surfaces historical patterns, models baselines, and grounding documents inform decisions before infrastructure is touched.

| # | Activity | Products Involved | NI's Role | Data Flow | Integration Mechanism | Outcome | Status |
|---|---|---|---|---|---|---|---|
| D0-1 | **Network capacity planning** | NI + SevOne | NI ingests historical SevOne metric data to model traffic baselines, peak utilization, and headroom per network segment | SevOne historical batch data → NI | SDP batch ingestion | Capacity recommendations with confidence intervals grounded in real traffic history | ✅ |
| D0-2 | **Anomaly baseline modeling** | NI + SevOne | NI's Granite time-series models build anomaly detection thresholds calibrated to actual historical device behavior | SevOne historical metrics → NI | Kafka / SDP batch | Individualized, per-device baselines for Day 2 anomaly detection — fewer false positives from day one | ✅ |
| D0-3 | **Network topology design review** | NI + SevOne | NI's chat assistant analyzes historical topology data and performance patterns to surface design recommendations and risk areas | SevOne metrics → NI | Kafka | Topology design validation report generated via NI chat assistant | 🔶 |
| D0-4 | **DNS zone architecture design** | NI + NS1 | NI models traffic patterns and application distribution needs; NS1 Filter Chain policies and Pulsar RUM thresholds are designed based on NI's analysis | SevOne + NI analysis → NS1 design | NI chat (output) → NS1 API provisioning | Optimal Filter Chain topology and Pulsar threshold configuration defined before go-live | 🔶 |
| D0-5 | **Grounding document ingestion** | NI | MOPs (methods of procedure), configuration guides, vendor runbooks, and network design documents loaded into NI as context for AI reasoning | Document upload → NI | NI Grounding Documents feature | AI reasoning grounded in organization-specific network context from day one | ✅ |
| D0-6 | **SLA definition & risk modeling** | NI + Concert Optimize | Concert Optimize provides resource demand forecasts; NI contributes network performance baselines to define achievable SLA targets | Concert Optimize telemetry → shared context | Concert API → NI (architectural) | SLA thresholds defined with AI-modeled confidence; risk areas flagged pre-deployment | 🔶 |
| D0-7 | **Security posture baseline** | NI + Concert Protect | Concert Protect scans planned network topology for vulnerability exposure; NI grounding documents include security posture requirements | Concert Protect findings → NI context | Concert → NI (architectural) | Security considerations embedded into network design before deployment | 🔶 |

---

## DAY 1 — Deployment & Provisioning

NI's role on Day 1: **Active deployment supervisor** — monitors onboarding health, orchestrates provisioning steps via Skills, validates baselines, and tunes first-alert policies.

| # | Activity | Products Involved | NI's Role | Data Flow | Integration Mechanism | Outcome | Status |
|---|---|---|---|---|---|---|---|
| D1-1 | **Device onboarding & discovery** | NI + SevOne | NI monitors real-time telemetry from newly provisioned devices; validates metric streams are healthy and complete; alerts if device onboarding is anomalous | SevOne Kafka stream (new devices) → NI | Kafka / SDP | Onboarding anomalies detected within minutes; NOC notified before issues escalate | ✅ |
| D1-2 | **DNS record provisioning** | NI + NS1 | NI Skills trigger NS1 REST API calls to create DNS zones and records for newly deployed services; Concert Workflows orchestrates the full provisioning sequence | NI Skills → Tool Management → NS1 REST API | Service API (OpenAPI) via NI Tool Management | DNS records provisioned automatically as part of service deployment workflow | 🔶 |
| D1-3 | **Traffic policy activation** | NI + NS1 | NI activates pre-designed NS1 Filter Chain policies for newly deployed services; Pulsar RUM monitoring activated for new endpoints | NI → NS1 REST API (Filter Chain, Monitors) | Service API via Tool Management | Traffic steering policies live within minutes of service deployment; RUM data collection begins immediately | 🔶 |
| D1-4 | **Monitoring baseline establishment** | NI + SevOne | SevOne begins streaming telemetry for new devices; NI Granite models establish initial per-device baselines during the first observation window | SevOne streaming metrics → NI | Kafka / SDP | Per-device, ML-calibrated baselines established; Day 2 anomaly detection is accurate from day one | ✅ |
| D1-5 | **First-alert policy tuning** | NI + SevOne + Concert | NI analyzes early telemetry patterns to recommend optimal alerting thresholds; Concert Operate configured to receive NI-enriched alerts | NI analysis → Concert Operate webhook | Webhook / Concert API | Alert policies tuned to actual behavior; reduces Day 2 alert noise from the start | 🔶 |
| D1-6 | **Provisioning validation** | NI + SevOne + Concert | NI validates that provisioned devices are performing within expected baselines; discrepancies trigger Concert Workflows for remediation | SevOne metrics → NI → Concert Workflows (if anomaly) | Kafka → NI → OpenAPI Tool call | Automated provisioning validation; misconfigurations caught and ticketed before service goes live | 🔶 |
| D1-7 | **Grounding document update** | NI | NI Skills workflows trigger updates to grounding documents with new device configurations, network maps, and deployment-specific MOPs after each provisioning step | Internal NI document management | NI Grounding Documents + Skills | Knowledge base kept current through the deployment lifecycle; Day 2 AI reasoning reflects actual deployed state | ✅ |
| D1-8 | **Post-deployment health gate** | NI + SevOne + Concert Resilience | NI generates a deployment health report; Concert Resilience records the initial resilience posture score; human operator approves Day 2 go-live | SevOne metrics → NI → Concert Resilience | NI chat + Concert API | Auditable go-live gate with AI-assessed network health and resilience baseline | 🔶 |

---

## DAY 2 — Operations & Optimization

NI's role on Day 2: **Autonomous brain** — continuous anomaly detection, multi-hypothesis root-cause analysis, orchestrated remediation across SevOne, Concert, and NS1 with graduated autonomy.

| # | Activity | Products Involved | NI's Role | Data Flow | Integration Mechanism | Outcome | Status |
|---|---|---|---|---|---|---|---|
| D2-1 | **Continuous anomaly detection** | NI + SevOne | NI's Granite time-series foundation models continuously analyze SevOne metric and alarm streams; detects silent degradations threshold-based tools miss | SevOne Kafka stream → NI | Kafka / SDP | Early-warning anomaly detection across all monitored devices; observations surfaced on NI dashboard | ✅ |
| D2-2 | **Investigation ticket generation** | NI | NI automatically generates investigation tickets for the highest-impact anomalies; each ticket initiates an agentic AI investigation | NI internal | NI Investigations feature | Critical anomalies immediately escalated to investigation; no manual triage required | ✅ |
| D2-3 | **Multi-hypothesis root-cause analysis** | NI + SevOne | Agentic AI generates multiple ranked root-cause hypotheses by correlating SevOne metrics, alarms, topology context, and grounding documents | SevOne streaming data + NI grounding docs | Kafka → NI reasoning agents | Ranked root-cause hypotheses with confidence scores presented to operators; reduces MTTR | ✅ |
| D2-4 | **AI-generated remediation plan** | NI | NI generates a step-by-step remediation plan grounded in MOPs, config guides, and domain knowledge; plan can be auto-executed or human-approved | NI grounding documents + Granite reasoning | NI Investigations + Tool Management | Actionable remediation plan in seconds vs. hours of manual investigation | ✅ |
| D2-5 | **Automated ITSM ticketing** | NI + Concert | NI triggers Concert Workflows to create a ServiceNow ticket with pre-populated root-cause, hypothesis, and recommended remediation steps | NI → Concert Workflows API → ServiceNow | Service API via Tool Management + Concert Workflows | Incident tickets created automatically with AI context; NOC team informed without manual effort | ✅ |
| D2-6 | **Network traffic re-routing via DNS** | NI + NS1 | NI detects performance degradation with DNS/CDN root cause; agentic AI calls NS1 REST API to update Filter Chain routing weights or activate failover | NI analysis → NS1 REST API (Filter Chain update) | Service API via Tool Management (approval optional) | Traffic re-routed at DNS level within seconds; application performance restored without infrastructure changes | 🔶 |
| D2-7 | **CDN / endpoint failover** | NI + NS1 | NI detects CDN endpoint failure via SevOne performance metrics + NS1 Pulsar RUM data; triggers NS1 Monitor to initiate automatic failover to backup endpoint | SevOne metrics + NS1 Pulsar → NI → NS1 API | Kafka + MCP/API → NI → Tool Management | Failover executed before users experience downtime; MTBI reduced significantly | 🔶 |
| D2-8 | **Cross-domain incident correlation** | NI + Concert Operate | NI contributes network-layer root cause to Concert Operate's unified incident view; Concert correlates with app-layer signals from Instana for full-stack context | NI findings → Concert Operate | Webhook / Concert API | Single unified incident view with both network and application context; faster resolution across ITOps and NetOps | 🔶 |
| D2-9 | **Automated runbook execution** | NI + Concert Workflows | NI triggers Concert Workflows to execute predefined runbooks (Terraform, CLI, API sequences) for network device remediation | NI remediation plan → Concert Workflows API | Service API via Tool Management | Runbooks executed automatically from AI-generated remediation plan; eliminates manual runbook lookup and execution | ✅ |
| D2-10 | **Resource right-sizing** | NI + Concert Optimize | NI identifies consistently over/under-utilized network resources; Concert Optimize correlates with compute and cloud demand to produce right-sizing recommendations | NI observations → Concert Optimize | Concert API (architectural) | Infrastructure costs reduced; performance maintained; capacity recommendations grounded in real usage | 🔶 |
| D2-11 | **Performance optimization (Pulsar)** | NI + NS1 | NI analyzes long-term SevOne traffic patterns; recommends NS1 Pulsar threshold adjustments for better long-term RUM-based routing performance | SevOne historical + NI → NS1 API | Service API via Tool Management | NS1 Pulsar continuously optimized based on AI analysis of real traffic behavior | 🔶 |
| D2-12 | **Proactive capacity expansion alert** | NI + SevOne + Concert | NI detects trend toward capacity limit (e.g., interface utilization approaching saturation); generates pre-emptive alert and triggers Concert Workflows for capacity request | SevOne metrics trend → NI → Concert Workflows (ticket) | Kafka → NI → Service API | Capacity issues addressed before they become incidents; shift from reactive to proactive operations | ✅ |
| D2-13 | **Resilience posture monitoring** | NI + Concert Resilience | NI feeds network resilience signals into Concert Resilience; Concert tracks posture score changes over time; gaps trigger NI investigation | NI anomaly history → Concert Resilience | Concert API (architectural) | Continuous resilience posture visibility; risks surfaced before they cause incidents | 🔶 |
| D2-14 | **Post-incident learning** | NI | NI updates grounding documents with new findings from completed investigations; future root-cause hypotheses benefit from accumulated organizational knowledge | NI internal (Investigation results → Grounding Documents) | NI Grounding Documents + Skills | Self-improving AI system — each incident makes future investigations faster and more accurate | ✅ |
| D2-15 | **Security anomaly detection** | NI + SevOne + Concert Protect | NI detects unusual traffic patterns (potential DDoS, lateral movement); Concert Protect correlates with vulnerability data; combined alert to security team | SevOne traffic anomaly → NI → Concert Protect API | Kafka → NI → Concert API | Security anomalies detected at network layer and correlated with security posture for prioritized response | 🔶 |

---

## Summary: NI's Role Per Day

| Day | NI's Primary Role | Key NI Capability Used | Primary Data Consumer | Primary Action Trigger |
|---|---|---|---|---|
| **Day 0** | Analytical intelligence layer — surfaces insights from historical data to inform design | Chat assistant, Grounding Documents, Investigations (historical) | SevOne (historical batch) | Human decision (NI advises) |
| **Day 1** | Active deployment supervisor — monitors health, orchestrates provisioning steps | Skills, Tool Management, real-time dashboard | SevOne (live stream starts) | Skills + human approval gates |
| **Day 2** | Autonomous brain — detect, reason, remediate continuously | Investigations, Agentic AI, Tool Management, A2A | SevOne (continuous Kafka stream) | Autonomous or approval-gated |

---

## Graduated Autonomy Model

NI supports a **progressive autonomy path** — organizations choose how much AI autonomy to grant over time:

```
Stage 1 — Assisted:    NI detects + recommends → Human reviews + executes manually
Stage 2 — Supervised:  NI detects + plans → Human approves → NI executes via Tool Management
Stage 3 — Autonomous:  NI detects + plans + executes → Human reviews post-action
Stage 4 — Self-Healing: NI detects + executes + validates + learns → Human sets policy only
```

Each Tool Management integration (SevOne API, Concert Workflows, NS1 API) can be individually set to **"Requires approval"** or **"No approval required"** — enabling mixed autonomy where, for example, DNS traffic re-routing is autonomous but device configuration changes require approval.
