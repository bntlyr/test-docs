# Master Data: Material, Raw Material, Material Group, Rotation & Melting (Metallurgy)

Controls metal alloy grades, ingot specifications, scrap rotation ratios, chemical recipes, and melting furnace standards.

---

## 1. Material (`Material`)

Represents standardized cast metal alloy specifications used in production (e.g., `SCS13`, `SCS14`, `SCS16`, `SUS304`, `SUS316`, `SCH13`).

* **Key Attributes**:
  * `code`: Material designation according to JIS / ASTM standards.
  * `name`: Descriptive name (e.g., Stainless Steel Casting SCS16).
  * `density`: Specific gravity / alloy density (g/cm³).
  * `shrinkageRate`: Thermal shrinkage percentage for tooling compensation.
  * `materialGroupId`: Linked chemical family (`MaterialGroup`).

---

## 2. Raw Material (`RawMaterial`)

The physical input forms of metals fed into the induction melting furnaces:
1. **Virgin Ingots**: New certified chemical ingots directly received from suppliers with Heat Certificates.
2. **Returns / Gating Scrap**: Internal gates, sprues, runners, and risers cut from poured trees.
3. **Purchased Scrap**: Clean qualified scrap material.

---

## 3. Material Group (`MaterialGroup`)

Categorizes materials into metallurgic families for furnace scheduling and chemical segregation:
* **Austenitic Stainless Steels** (300 series)
* **Martensitic / Ferritic Steels** (400 series)
* **Carbon & Low-Alloy Steels**
* **Heat-Resistant Alloys** (Cobalt/Nickel based)

> [!NOTE]
> Scheduling heats within the same Material Group prevents cross-contamination of refractory furnace linings and preserves chemical purity.

---

## 4. Raw Material Rotation (`RawMaterialRotation`)

Defines mandatory blending ratios between **Virgin Metal Ingots** and **Internal Return Scrap**:
* **Maximum Scrap Ratio**: Defines the allowable percentage of recycled gates/runners (e.g., 50% Virgin / 50% Return) to ensure tensile strength, elongation, and chemical tolerance compliance.

---

## 5. Melting Standards (`Melting`)

Defines high-temperature melting parameters for each alloy grade:
* **Tapping Temperature**: Target molten metal temperature (e.g., 1,580°C - 1,620°C).
* **Deoxidation Agents**: Required additions of Aluminum, Silicon, or Manganese during melt prep.
* **Spectrometer Testing Bounds**: Acceptable percentage ranges for Carbon, Chromium, Nickel, Molybdenum, Silicon, and Phosphorus.
