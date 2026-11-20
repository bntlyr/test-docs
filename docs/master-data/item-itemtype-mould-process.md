# Master Data: Item, ItemType, Mould, Mould Type & Process (Product Definition)

Defines CASTEM's precision manufactured parts, casting moulds, process routings, and technical production specifications.

---

## 1. Item (`Item`)

The core product record representing precision investment casting pieces, machined items, or sub-assemblies.

* **Key Attributes**:
  * `id`: Numeric identifier.
  * `itemCode`: Engineering part number (e.g., `10-00001-000`, `61-00170-120`).
  * `itemName`: Part name in English (e.g., `RECEIVER`, `TOP NUT MATERIAL`).
  * `itemNameJpn`: Japanese name translation for export documentation.
  * `description`: Engineering specifications and customer drawing references.
  * `stdItemWt`: **Standard Item Weight in grams**. Essential for:
    * Automatic conversion from piece counts to net weight in kilograms (`grams / 1000 * quantity`).
    * Pallet gross weight calculations during shipping.
  * `sellingPrice` & `unitPrice`: Commercial export prices used in Commercial Invoices and Sales Orders.
  * `materialId`: Linked base metal alloy (`Material`).
  * `mouldId`: Linked metal injection mould (`Mould`).
  * `itemTypeId`: Category classifier (`ItemType`).

---

## 2. Item Type (`ItemType`)

Categorizes products based on lifecycle status and market classification:
* **Types**: Standard Production, Prototype / Trial, Replacement Part, Tooling Component, Commercial Extra.

---

## 3. Mould & Mould Type (`Mould`, `MouldType`)

Defines precision metal injection moulds used to produce wax patterns for investment casting.

* **Attributes**:
  * `mouldCode`: Unique die identification code (e.g., `M-1024`).
  * `cavityCount`: Number of wax patterns produced per injection shot.
  * `mouldType`: Single Cavity, Multi-Cavity, Family Mould, Modular Insert.
  * `status`: Active, In-Maintenance, Retired.
* **Planning Impact**:
  * Determines tree/cluster assembly counts and wax pattern injection cycle times in production scheduling.

---

## 4. Process (`Process`)

Represents the standardized manufacturing routing stages in the lost-wax investment casting sequence:

```mermaid
flowchart LR
    Wax["1. Wax Injection"] --> Tree["2. Tree Assembly"]
    Tree --> Dip["3. Ceramic Slurry & Stuccoing"]
    Dip --> Dewax["4. Dewaxing & Pre-Heating"]
    Dewax --> Melt["5. Induction Melting & Pouring"]
    Melt --> Knockout["6. Shell Knockout & Cutting"]
    Knockout --> Grind["7. Gate Grinding & Heat Treatment"]
    Grind --> Inspection["8. Final Inspection & Boxing"]
```

* **Attributes**:
  * `processCode`: Short code (e.g., `WAX`, `DIP`, `MELT`, `CUT`, `GRD`, `HT`, `QA`).
  * `processName`: Full routing station name.
  * `sequence`: Default routing order index.
  * `standardCycleTime`: Standard seconds or minutes per piece for capacity calculation.
