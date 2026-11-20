# Production Planning: Master Plan & Order Scheduling

Translates confirmed customer Sales Orders into macro production schedules and factory targets.

---

## 1. Master Production Plan (`ProductionPlan`)

The central coordination vehicle linking commercial demand with factory throughput.

* **Key Attributes**:
  * `planNo`: Plan identifier (e.g., `PP-2026-10`).
  * `period`: Target planning month/year.
  * `targetOutputKg`: Target total cast metal weight in kilograms.
  * `targetPieces`: Target finished pieces.
  * `status`: `DRAFT`, `RELEASED`, `IN_EXECUTION`, `COMPLETED`.

---

## 2. Order Backlog & Requirement Netting

* **Gross Demand**: Evaluates all unfulfilled order lines from confirmed Sales Orders.
* **Safety Stock & Inventory Netting**: Deducts available unallocated Finished Goods (`FinishedGoodsLot`) to calculate the net required production quantity.
* **Scrap Allowance Multiplier**: Automatically increases production batch sizes based on historical scrap/defect rates for each specific item code (e.g., +8% for complex geometry pieces).

---

## 3. Milestones & Delivery Commitments

* **Target Pour Date**: The latest date by which molten metal must be poured to meet delivery.
* **Target Machining Date**: Required completion date for post-cast grinding, CNC machining, and heat treatment.
* **Target QA Date**: Deadline for final visual, dimensional, and dye penetrant inspection.
* **ETD Commitment**: Packaging and pallet staging deadline for export customs processing.
