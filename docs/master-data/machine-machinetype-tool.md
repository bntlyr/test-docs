# Master Data: Machine, Machine Type & Tool (Equipment & Tooling)

Defines factory machinery, furnace equipment, processing stations, and operational fixtures.

---

## 1. Machine (`Machine`)

Individual production assets and work centers across CASTEM's plant floor.

* **Key Attributes**:
  * `machineCode`: Machine identifier (e.g., `IND-FURN-01`, `WAX-INJ-04`, `SHOT-BLAST-02`).
  * `machineName`: Equipment name (e.g., 250kg Medium-Frequency Induction Furnace #1).
  * `machineTypeId`: Machinery classification (`MachineType`).
  * `sectionId`: Department where the machine is situated.
  * `capacityPerShift`: Rated output capacity per 8-hour shift.
  * `status`: Operational, Maintenance Downtime, Calibration, Decommissioned.
* **Planning Impact**:
  * Used by the **Load Capacity** monitoring dashboard to calculate machine utilization percentages, bottleneck warnings, and overload alerts.

---

## 2. Machine Type (`MachineType`)

Classifies machine categories across the shop floor:
* **Induction Furnaces** (Melting & Pouring)
* **Wax Injection Machines** (Pattern Making)
* **Ceramic Coating Robots / Slurry Tanks** (Shell Building)
* **Dewaxing Autoclaves** (Steam wax removal)
* **Cut-Off Machines** (Abrasive and Plasma cutting)
* **Grinding Stations & Belt Sanders** (Gate removal)
* **Heat Treatment Furnaces** (Annealing, Quenching, Tempering)
* **Shot Blast & Sand Blast Cabinets** (Surface finishing)

---

## 3. Tool (`Tool`)

Fixtures, jigs, cutting blades, grinding wheels, and inspection gauges attached to machines.

* **Key Attributes**:
  * `toolCode`: Tool inventory identifier.
  * `name`: Tool description (e.g., Diamond Cut-Off Disc 400mm, Thread Gauge M12x1.5).
  * `toolType`: Cutting Tool, Grinding Abrasive, Inspection Fixture, Tree Assembly Clamp.
  * `serviceLifeLimit`: Maximum operational cycles or pieces before replacement or re-sharpening.
