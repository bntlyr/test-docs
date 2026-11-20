# Master Data: Supplier & Customer (Business Partners)

This module maintains external commercial relationships with suppliers and clients.

---

## 1. Supplier (`Supplier`)

Represents vendors supplying raw materials, chemical ingots, scrap metals, packaging, and factory consumables.

* **Key Attributes**:
  * `id`: Numeric database identifier.
  * `name`: Supplier corporate entity name.
  * `code`: Unique vendor code (e.g., `SUP-001`).
  * `type`: Local vs. International / Import.
  * `currency`: Transaction currency (`PHP`, `USD`, `JPY`).
  * `taxId`: Official tax registration number.
  * `paymentTerms`: Commercial payment terms (e.g., `30 Days Net`, `Cash on Delivery`, `TT`).
  * `address` & `country`: Physical plant and headquarters location.
  * `contactPerson`, `contactNumber`, `emailAddress`: Primary procurement contact info.
* **Usage**:
  * Material procurement, ingot receiving, and chemical batch certificate of analysis (CoA) validation.

---

## 2. Customer (`Customer`)

Maintains client accounts who purchase precision investment casting products from CASTEM.

* **Key Attributes**:
  * `id`: Numeric database identifier.
  * `name`: Corporate client name (e.g., `CASTEM CO., LTD.`, `SATO METAL TRADING CO., LTD.`, `Asia Supply Line, LLC`).
  * `code`: Official customer abbreviation (e.g., `CJC`, `CAC`, `SATO`, `ASL`, `YCFMC`).
  * `type`: Local or Export (`Local`, `Overseas`).
  * `currency`: Commercial billing currency (`JPY`, `USD`, `PHP`).
    > [!IMPORTANT]
    > **Currency Standardization Rule**: Japanese Yen currency codes are strictly formatted and exported as **`JPY`** (never `JPN`) across all commercial invoices, packing lists, and export files.
  * `address` & `country`: Billing corporate address.
  * `shippingAddress`: Physical delivery destination port/plant.
  * `shippingContactPerson`, `shippingContactNumber`, `shippingEmailAddress`: Delivery receiving personnel.
  * `paymentTerms`: Commercial terms (e.g., `FOB Cavite, Philippines`, `CIF Osaka`, `T/T Remittance`).
* **Special Customer Rules**:
  * **Automatic Returnable Pallets (`CJC` / `CAC`)**:
    When the customer code is `CJC` (Castem Japan Co.) or `CAC` (Castem America Corp.), all pallets in shipments are automatically flagged as **Returnable Packing Materials (RPM)**, generating dedicated commercial declarations and line items on shipping invoices.
