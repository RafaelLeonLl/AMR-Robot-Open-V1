# AMR-Robot-Open-V1
University AMR project. Open code and docs (Apache-2.0 for code, CC BY 4.0 for docs).

> **Summary**  
> Low-cost skid–steer AMR validated on a bench. Focus on safety (speed limiting + E-Stop < 1 s), requirements traceability (StRS/SyRS), and a process aligned with **VDI 2206**.

## Highlights
- **Payload:** 15 kg (5 min without damage)  
- **Safe speed:** ≤ 0.30 m/s in human areas  
- **Target runtime:** 30 min per cycle  
- **Ramp:** 5° with 15 kg, no slip  
- **Base:** 2WD/4WD evaluated; decision by tech & cost criteria  
- **E-Stop:** traction to 0 in < 1 s

*(KPIs and requirements come from the project report: mission, operating environment, risks, StRS → SyRS, and minimum standards map.)*

## Repository layout


## Requirements & KPIs (extract)
- **StRS/SyRS** with measurable “shall” statements: speed ≤ 0.30 m/s, ramp 5°, E-Stop < 1 s, dimensions, noise, cost, 24 V LiFePO4 energy.  
- **Traceability:** Requirement → Function/Architecture → Test case → Evidence (log/video).

## Design & sizing (short)
Longitudinal dynamics for **force/torque**:  
\( F_{tot} = F_{rr} + F_{grade} + F_{drag} + ma + F_{\omega} \), with \( J_{eq} = N_w J_w + N_d G^2 J_m \).  
Wheel torque \( T_{wheel} = F_{tot} r_w \), motor torque \( T_m = T_{wheel}/(G \eta_g) \), traction check via friction \( \mu \).  
(Full derivations and numbers are in the project PDF.)

## VDI 2206 – How we applied it
- **C0 Definition/Feasibility:** mission, scope, KPIs, risks, go/no-go.  
- **C1 Requirements:** StRS → measurable SyRS + compliance policy + traceability.  
- **C2 Architecture/ICD:** context, alternatives (2WD vs 4WD), final decision, managed interfaces.  
- **C3 Domain design:** mechanical (reduction, chassis), electrical (24 V SELV), control (speed limit, E-Stop).  
- **V&V:** plan and evidence (PR-VELOC-01, PR-RAMPA-01, PR-ESTOP-01).

## Minimum standards (academic prototype)
- **ISO 3691-4 (AMR/AGV):** safe speed and **Emergency Stop**.  
- **SELV 24 V:** safe power (fuse/isolator, polarity).  
- **Basic signaling:** visual/audible while moving.  
Mapping: Requirement → clause/criterion → method (Test/Demo/Inspection/Analysis). See the PDF for the full table.
