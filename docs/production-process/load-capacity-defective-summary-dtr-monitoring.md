# Production Process: Load Capacity, Defective Summary, DTR & Monitoring

Provides managers and quality engineers with actionable visibility into machine workloads, yield rates, operator output, and real-time process bottlenecks.

---

## 1. Load Capacity Monitoring (`LoadCapacity`)

Monitors machine and workstation utilization against rated capacity.

* **Key Metrics**:
  * **Planned Hours vs Available Capacity Hours**: Visualized by workstation and machine group.
  * **Utilization Percentage**: `(Scheduled Machine Time / Available Shift Time) * 100`.
  * **Bottleneck Alerts**: Highlighted indicators for workstations exceeding 85% and 100% capacity thresholds.
* **Planning Intervention**:
  * Allows planners to balance schedules by opening secondary shifts or re-routing parts to equivalent machines.

---

## 2. Defective Summary Analysis (`DefectiveSummary`)

Aggregates defect reports logged during process booking to drive continuous quality improvement (Kaizen) and scrap reduction.

* **Defect Categorization**:
  * **Casting Defects**: Shrinkage porosity, gas holes, cold shuts, misruns, slag inclusions.
  * **Pattern Defects**: Wax pattern distortion, broken cores, surface sink marks.
  * **Finishing / Grinding Defects**: Over-grinding, undercut, surface cracks.
  * **Dimensional & Visual Defects**: Out of tolerance, warp, cosmetic blemishes.
* **Pareto & Trend Analysis**:
  * Identifies top contributing defect causes by item code, mould number, and operator shift.

---

## 3. Daily Time Record Summary (`DTR Summary`)

Tracks operator productivity, labor efficiency, machine hours, and piece output.

* **Full Item Code Resolution**:
  > [!IMPORTANT]
  > The DTR Summary Inquiry displays the **Full Item Code** (e.g., `10-00001-000`, `61-00170-120`) alongside fabrication codes, ensuring clear traceability across accounting and engineering teams.
* **Tracked Data**:
  * Operator name, section, and shift.
  * Total pieces processed per station.
  * Standard vs. actual time variance.

---

## 4. Real-Time Process Monitoring Inquiry (`Monitoring`)

A live shop floor dashboard showing the status of all active production lots:
* Searchable by Item Code, Lot Number, Process Station, Charge Number, or Date Range.
* Color-coded progress indicators: In-Process (Blue), Inspection Hold (Yellow), Completed (Green), Delayed (Red).
