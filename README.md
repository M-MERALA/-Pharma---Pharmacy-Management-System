# 💊 Pharma - Luxury Pharmacy Management System

Pharma is an elegant, modern desktop Pharmacy Management System built with **Java 17** and **JavaFX**. It features a stunning, animated **Emerald-Teal Glassmorphism UI** and showcases **16 different Gang-of-Four (GoF) design patterns** for a highly modular, professional, and scalable enterprise codebase.

The application operates entirely in-memory via a synchronized local data warehouse. It runs with zero database latency, making it highly portable and ready for immediate local testing.

---

## 🚀 Key Features

*   **Luxury User Interface**: Stunning visual branding with custom glassmorphism overlays, soft gradient backgrounds, responsive grids, and clean visual cards.
*   **Programmatic Vector Branding**: Features a custom-drawn SVG medical logo emblem (spliced heart, serpent, and capsule pill detail) rendered programmatically in JavaFX with glowing gradients and zero image dependencies.
*   **Animated Splash Screen**: Features high-fidelity launch animations (fade, scale-up, slide-in) and a heartbeat pulsing loop applied directly to the vector emblem.
*   **Dynamic POS (Point of Sale)**: Interactive cashier terminal where users can build a checkout cart, adjust quantities, calculate taxes/delivery/discounts dynamically, and execute payments.
*   **Multi-strategy Payments**: Settles orders using Cash, Card, or a simulated external Insurance API.
*   **Inventory & State Monitoring**: Automatically monitors inventory levels, changing drug states (`Available`, `Low Stock`, `Out of Stock`, `Expired`) and displaying colored status badges across the system.
*   **Undoable Command Log**: Administrators can track modifications to the medicine catalog, allowing instant undo actions (like reversing a drug deletion).
*   **Support & Prescription Requests**: Patients can submit medicine/prescription requests. Pharmacists can review them, reply, and update request states (`Pending` -> `Reviewed` -> `Completed`).
*   **Modular Reporting**: Generates custom sales, inventory, revenue, and customer activity logs.

---

## 🧠 Design Patterns Implemented (16 Total)

The architecture is built around professional software engineering patterns:

### Creational
1.  **Singleton (`DataStore`, `SessionManager`)**: Guarantees a single in-memory database instance and tracks current user sessions across screens.
2.  **Factory Method (`UserFactory`)**: Instantiates specific user classes (`AdminUser`, `PharmacistUser`, `CustomerUser`) dynamically.
3.  **Abstract Factory (`UIFactory`, `LuxuryUIFactory`)**: Programmatically creates styled controls conforming to the Emerald-Teal visual design.
4.  **Builder (`InvoiceBuilder`, `CustomerRequestBuilder`)**: Assembles complex billing transactions and multi-property request tickets step-by-step.
5.  **Prototype (`Medicine`)**: Implements the clone interface, allowing administrators to duplicate similar medicines to accelerate catalog entry.

### Structural
6.  **Proxy (`ScreenAccessProxy`)**: Intercepts sidebar and workspace navigation, evaluating user role permissions before displaying restricted dashboards.
7.  **Facade (`PharmacyFacade`)**: Simplifies complex backend calls by grouping inventory updates, transaction logging, and observer notifications under a single checkout call.
8.  **Adapter (`InsuranceAdapter`)**: Adapts a simulated third-party `ExternalInsuranceAPI` to fit the system's standard billing interfaces.
9.  **Decorator (`InvoicePricingDecorator`)**: Wraps base pricing with dynamic combinations of charges, such as VAT, home delivery, or discount multipliers.
10. **Composite (`MedicineComponent`, `MedicineCategory`)**: Organizes the drug catalog into a tree directory of categories and products, treating single items and folders uniformly.

### Behavioral
11. **Observer (`InventorySubject`, `InventoryObserver`)**: Alerts active system layouts and dashboards to update statistics instantly when stock levels drop.
12. **Strategy (`PaymentStrategy`)**: Dynamically swaps cash, credit, or insurance checkout algorithms.
13. **Command (`MedicineCommand`, `CommandInvoker`)**: Wraps catalog alterations into command objects to maintain an active log of undoable transactions.
14. **State (`MedicineState`, `RequestState`)**: Models drug inventory statuses (`Available`, `OutOfStock`, `Expired`) and customer ticket reviews (`Pending`, `Completed`).
15. **Template Method (`ReportTemplate`)**: Standardizes report formatting, leaving data extraction to concrete reports.
16. **Chain of Responsibility (`PrescriptionHandler`)**: Forwards prescription verification through custom verification levels (`PharmacistHandler` -> `ManagerHandler`).

---

## 🛠️ Tech Stack & Architecture

*   **Language**: Java 17 (OOP, Custom collections, Streams, Multi-threading timers)
*   **GUI Framework**: JavaFX 17 (Scene Graph, CSS Stylesheets, Custom SVGs, Transition Animations)
*   **Build Tool**: Maven 3.8+
*   **Styling**: Vanilla CSS (Styles, Gradients, Translucency, Drop Shadows)
*   **Data Tier**: In-memory database with pre-populated sample records

---

## 🖥️ Screen Previews & Workflows

1.  **Splash Screen**: Programmatic logo rendering, entrance animations, and heartbeat loops.
2.  **Login Panel**: Role-based entrance with quick registration switches.
3.  **Dashboard**: Statistical highlights, dynamic action lists, and real-time alerts.
4.  **POS Terminal**: Interactive drug catalogs, shopping cart drawer, payment strategy panels.
5.  **Medicine Management**: Dynamic CRUD controls, catalog duplicating tools, catalog trees, and undo operations.
6.  **Customer Requests**: Live chat-like inbox for prescription reviews.
7.  **Analytical Reports**: Template-generated system reports.

---

## ⚡ Installation & Execution

### Prerequisites
*   **Java Development Kit (JDK)**: Version 17 or higher
*   **Apache Maven**: Version 3.8+

### How to Run
1.  Clone this repository:
    ```bash
    git clone https://github.com/yourusername/pharma-management.git
    cd pharma-management
    ```
2.  Launch the application using the Maven wrapper:
    *   **Windows (PowerShell)**:
        ```powershell
        .\mvnw.cmd clean javafx:run
        ```
    *   **Linux / macOS**:
        ```bash
        chmod +x mvnw
        ./mvnw clean javafx:run
        ```

### Demo Accounts & Credentials
The system launches preloaded with sample data for quick validation. Use the following default credentials:

| Role | Username | Password | Key Workflows to Test |
| :--- | :--- | :--- | :--- |
| **Admin** | `admin` | `admin123` | Clone catalog medicines, delete & undo records, generate custom reports |
| **Pharmacist** | `pharmacist` | `pharm123` | Open POS, checkout orders, review customer prescription requests |
| **Customer** | `customer` | `cust123` | Browse storefront, add items to cart, select payments, submit requests |

# 📸 Screenshots

![Screen1](https://raw.githubusercontent.com/USERNAME/REPO/main/screen1.png)

![Screen2](https://raw.githubusercontent.com/USERNAME/REPO/main/screen2.png)
