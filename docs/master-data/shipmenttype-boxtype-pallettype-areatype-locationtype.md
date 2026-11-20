# Master Data: ShipmentType, Box Type, Pallet Type, Area Type & Location Type (Logistics & Storage)

Defines packaging standards, container weights, tare values, returnable pallet pricing, and warehouse topological structures.

---

## 1. Shipment Type (`ShipmentType`)

Specifies export and domestic delivery transport modes:
* **AIR**: Airfreight shipping (stricter weight constraints: default max 300 kg per pallet).
* **SEA**: Ocean container shipping (FCL / LCL shipments, larger volumetric capacities).
* **LAND / LOCAL**: Domestic truck delivery within the Philippines.

---

## 2. Box Type (`BoxType`)

Defines standard corrugated cardboard carton boxes used to pack finished goods for export.

* **Key Attributes**:
  * `code`: Box carton code (e.g., `BX-STD-01`, `BX-HVY-02`).
  * `name`: Carton model name (e.g., Heavy Duty Double Wall Carton).
  * `weight`: **Tare weight in kilograms** of the empty box (e.g., 0.65 kg).
  * `dimensions`: Length x Width x Height.

---

## 3. Pallet Type (`PalletType`)

Defines plastic and wooden pallets used to consolidate finished goods boxes into transport units.

* **Key Attributes**:
  * `name`: Pallet designation (e.g., `PLASTIC PALLET #1`, `STEEL BASKET`, `HALF PALLET`).
  * `type`: Material category (`PLASTIC`, `STEEL`, `WOOD`).
  * `description`: Dimensions and load specifications (e.g., `L110 x W110 x H14 cm`).
  * `weight`: **Tare weight in kilograms** (e.g., 8.00 kg, 15.40 kg, 21.00 kg, 36.00 kg).
  * `unitPrice`: Commercial export unit price in **JPY** (default fallback: **¥3,300 JPY** for plastic returnable pallets).
* **Returnable Packing Material (RPM) Impact**:
  * When shipping to returnable pallet customers (such as `CJC` or `CAC`), the pallet's `unitPrice` and computed line amount (`palletCount * unitPrice`) are automatically generated in the **Commercial Invoice (PDF/Excel)**, declared as reusable packaging, and totaled into the Grand Total value.

---

## 4. Area Type (`AreaType`)

High-level warehouse geographical zones:
* **RAW-MAT**: Raw Material & Ingot Storage
* **WIP-AREA**: Work-in-Progress Staging Zones by Process
* **FG-WH**: Finished Goods Warehouse
* **QA-HOLD**: Quality Inspection / Quarantine Hold Area
* **DISPATCH**: Pallet Assembly and Shipping Staging Bay

---

## 5. Location Type (`LocationType`)

Specific addressable bin, rack, and shelf coordinates within an Area:
* **Coordinate Format**: `Aisle - Rack - Shelf - Bin` (e.g., `FG-A01-R02-B04`).
* **Attributes**:
  * `areaTypeId`: Parent storage zone.
  * `maxCapacity`: Max box or weight limit.
  * `isOccupied`: Real-time availability indicator.
