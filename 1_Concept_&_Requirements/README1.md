

Integration area = cross-cutting theme a driver/judge experiences that multiple subsystems must satisfy.

Each attribute should be turned into a verifiable requirement (with a method: Test, Demo, Inspection, Analysis), and traced in a VCRI/compliance matrix. 

Automotive Systems Engineering …

 

Automotive Systems Engineering …

Keep requirements verifiable, unambiguous, implementation-free, necessary—then plan verification on the right side of the V. 

Automotive Systems Engineering …

 

Automotive Systems Engineering …

1) Vehicle dynamics & control (driveability/handling)

Attributes: tip-in latency, torque rise time, jerk limit, braking distance/decel, straight-line stability, on-center steering feel, speed-tracking RMS.
Example targets: tip-in ≤150 ms; torque rise ≤300 ms; jerk ≤3 m/s³; RMS speed error ≤1 km/h (flat).
Verification: instrumented straight-line tests + Simulink driver-glider runs; log pass/fail against requirement IDs in the VCRI. (Use baseline simulations and coverage of modes/decisions.) 

Automotive Systems Engineering …

 

Automotive Systems Engineering …

2) Energy & power budget

Attributes: Wh/lap (or Wh/km), SoC reserve at finish, power availability vs. grade, regen capability, 12 V aux budget.
Targets: “Complete N laps ≤ E_budget; finish SoC ≥ X%.”
Verification: analysis vs. road-load models; per-lap energy logs within a tolerance; keep baseline runs to detect regressions. 

Automotive Systems Engineering …

3) Solar energy harvest (Solar Car only)

Attributes: MPPT tracking error, daily Wh harvested, thermal derate of array/MPPT, shading robustness, forecast accuracy.
Targets: MPPT error ≤1% of MPP; array Wh/day ≥ stage plan; derate slope ≤spec.
Verification: sun-sim/field IV-sweeps (Test/Demo) + Analysis vs. forecast; record in VCRI. 

Automotive Systems Engineering …

4) Thermal management

Attributes: component temps vs. limits (cells, inverter, motor, brakes), heat-rejection capacity at worst ambient, fan power.
Targets: e.g., cell core ≤45 °C @ 35 °C amb; inverter ≤90 °C; no brake fade >10%.
Verification: 1-D/FEA thermal models with validation sampling at specific times/modes, then instrumented laps; track conservation/energy-balance checks. 

Automotive Systems Engineering …

5) Aerodynamics & body

Attributes: CdA, lift balance, crosswind sensitivity, cooling drag, sealing.
Targets: CdA ≤X m²; side-force gain ≤Y N/deg; cooling drag ≤Z% of total.
Verification: CFD ↔ coast-down/tunnel correlation; keep baseline datasets and coverage so changes are caught. 

Automotive Systems Engineering …

6) Structure, chassis, mass

Attributes: mass budget by subsystem, torsional stiffness, rule-mandated safety (rollover/crash), manufacturability & tolerances (GD&T).
Targets: curb mass ≤M_target (±1% weigh-in); torsional stiffness ≥k Nm/deg.
Verification: weigh-ins, torsion rigs, inspection of drawings vs. BoM; tie evidence to requirement IDs. (FCA/PCA later confirm as-built vs. as-designed.) 

Automotive Systems Engineering …

7) Electrical integration, EMC, and HV safety

Attributes: HVIL integrity, insulation resistance, fault-to-torque-inhibit time, EMI/EMC emissions/susceptibility, voltage-drop budget, labeling/serviceability.
Targets: IR ≥1 MΩ @ 500 V; HVIL-open → torque-inhibit <10 ms; LV drop <5%.
Verification: Inspection (labeling), Test (IR/HiPot/HVIL pulls), Analysis (drops), chamber or near-field checks; log in VCRI. 

Automotive Systems Engineering …

8) HMI, ergonomics & driver ops (“easy to drive”)

Attributes: pedal/steer/brake mapping linearity, steering torque vs. lateral g, visibility, startup/shutdown flow, alert salience/latency.
Targets: accel-pedal linearity ±5%; alert latency ≤200 ms; visibility envelope pass (95th pct).
Verification: Demo (procedures), Test (instrumented laps & clinics), Inspection (controls), Analysis (task times). Keep requirements implementation-free to avoid over-specifying “how.” 

Automotive Systems Engineering …

9) Data, telemetry & strategy

Attributes: telemetry latency & loss, logging rate/completeness, time sync, model↔real strategy loop integrity.
Targets: latency ≤1 s; packet loss <1%; ≥10 Hz logs for key channels; clock skew <50 ms.
Verification: Test (range and packet-loss), Analysis (log audits), coverage to ensure all modes/paths exercised. 

Automotive Systems Engineering …

10) Compliance, safety case & rules

Attributes: scrutineering readiness, documentation completeness, hazard/risk closure, change control & configuration.
Targets: zero critical findings; all artifacts current to baseline.
Verification: Inspection (docs), Audits (internal), configuration management of models/artifacts. 

Automotive Systems Engineering …

Turning attributes into requirements (template)

For each attribute, capture: metric(s) → target & conditions → method (T/D/I/A) → impacted subsystems → interfaces/budgets → evidence link (VCRI row). SAE emphasizes making requirements verifiable and keeping a VCRI/compliance matrix with each spec. 

Automotive Systems Engineering …

 

Automotive Systems Engineering …

Example (“Easy to drive—responsive accel without jerk”)
Metrics: tip-in latency, torque rise, jerk. Targets: ≤150 ms, ≤300 ms, ≤3 m/s³ @ 20 °C, flat. Method: Test (instrumented runs) + Analysis (model correlation). Trace: VCRI-DYN-001..003. (Good requirement traits: verifiable, unambiguous, implementation-free.) 

Automotive Systems Engineering …

Budgets that bind integration areas

Keep and review these continuously (left↔right of the V): mass, power/energy, thermal, aero (cooling drag vs. CdA), electrical (voltage drop/current limits/fusing), latency. Use baseline simulations, mode/time sampling, conservation checks, and coverage analysis to keep models trustworthy as you iterate. 

Automotive Systems Engineering …

Where these sit on the V and at reviews

Define attributes & initial budgets in SRR/SFR; show decomposition & interfaces. 

Automotive Systems Engineering …

Prove feasibility with analyses at PDR; lock designs & verification plans at CDR. 

Automotive Systems Engineering …

Execute procedures at TRR; close evidence at QR/ORR; confirm as-built with FCA/PCA. 

Automotive Systems Engineering …

Why these sources?

Requirements & Testing → what makes a good requirement, T/D/I/A methods, VCRI/compliance matrix discipline. 

Automotive Systems Engineering …

 

Automotive Systems Engineering …

Approach & Verification → model V&V: baselines, sampling of modes/times, conservation, coverage—practical checks you’ll use in labs. 

Automotive Systems Engineering …

Modeling → how to choose/formalize modeling approaches across domains (block/causal vs. acausal, multi-domain). 

Automotive Systems Engineering …

Overview → lifecycle framing & SE definitions; place your work correctly on the V and at reviews. 

Automotive Systems Engineering …

If you want, I can turn this into a CSV “Integration Attribute Spec” (one row per attribute) pre-filled for Supermileage and Solar Car, ready to drop into your repo and wire to your VCRI.