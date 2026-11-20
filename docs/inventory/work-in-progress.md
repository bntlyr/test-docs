# Inventory: Work In Progress (WIP)

Tracks parts currently undergoing active manufacturing, chemical treatment, or inspection between the initial wax pattern and final finished packaging.

---

## 1. What is Work In Progress in Investment Casting?

In investment casting, products undergo multiple physical transformations:

1. **Wax Pattern Stage**: Individual wax patterns injected from metal moulds.
2. **Tree / Cluster Assembly Stage**: Wax patterns welded onto central wax runners and pouring cups.
3. **Ceramic Shell Stage**: Wax trees coated with ceramic slurry and stucco refractory grains (multiple coats, drying cycles).
4. **Melt & Poured Stage**: Molten steel poured into fired ceramic shells under high vacuum/atmospheric induction.
5. **Cut-Off & Knockout Stage**: Ceramic shell mechanically vibrated off; individual cast parts cut off the tree.
6. **Finishing & Grinding Stage**: Gate stubs ground flush; heat treatment (annealing/quenching) applied.
7. **Surface Treatment Stage**: Shot blasting, sand blasting, acid pickling, passivation.
8. **Final QA Inspection Stage**: Dimensional checks, visual inspection, non-destructive testing (NDT/dye penetrant).

---

## 2. WIP Tracking Dimensions

* **Lot / Batch Number**: Every batch carries a routing traveler (Operation Slip) detailing:
  * Part Item Code and Description.
  * Charge Heat Number (identifying the specific furnace melt).
  * Current Process Routing Station.
  * Good Piece Count.
  * Defective / Scrap Piece Count with defect cause codes.
  * In-Process Hold / Rework Status.
* **WIP Valuation**:
  * Reflects accumulated raw material cost plus standard labor and machine cycle overhead absorbed at each completed process step.

---

## 3. Real-Time Shop Floor Interlocks

* **Early-Start Controls**: Prevents unauthorized initiation of downstream processes before preceding quality inspections are recorded and authorized by section supervisors.
* **Scrap Logging**: Rejected pieces at any station automatically credit back to the return scrap inventory and record defect statistics into the Defective Summary dashboard.
