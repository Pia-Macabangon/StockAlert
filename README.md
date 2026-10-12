# StockAlert

**Clear inventory control. Rapid emergency response.**

<p align="center">
  <img src="screenshots/login.png" alt="StockAlert Login Interface" width="550" />
</p>

A standalone Java desktop application for managing emergency medical supplies, tracking response vehicles, organizing personnel, and coordinating disaster dispatch. Built with Java Swing and backed by MySQL.

The system combines supply tracking with fleet and responder logistics into a single desktop dashboard. There is no external web server or complex cloud configuration required.

---

## Installation

### In Apache NetBeans (Recommended)
1. Clone or open the repository:
   ```bash
   git clone https://github.com/Pia-Macabangon/StockAlert.git
   ```
2. Open **Apache NetBeans**.
3. Navigate to **File** > **Open Project...** and select the `StockManagementSystem` directory.
4. NetBeans will automatically detect the Ant project, Swing forms (`.form`), and dependencies.

### In Visual Studio Code
1. Open the `StockManagementSystem` folder in VS Code.
2. Install the **Extension Pack for Java**.
3. Add the required libraries (`mysql-connector-j` and `AbsoluteLayout`) to your referenced libraries.

---

## Prerequisites & Database Setup

The application connects via JDBC to a local MySQL server (port `3306`) with username `root` and default password (empty `""`):

- **Java JDK**: Version 8 or newer
- **Database Server**: MySQL (e.g. via XAMPP, WampServer, or standalone MySQL service)
- **Databases**:
  - `java_medical` / `java_stock`: Supplies, inventory stock levels, expiration dates, and billing
  - `java_vehicle`: Response fleet vehicles, availability, and vehicle allocations
  - `java_personnel`: Staff and emergency responder directories

---

## Default Login

| Field | Value |
| :--- | :--- |
| **Username** | `admin` |
| **Password** | `1234` |

---

## Modules

| Module | What it manages | Key actions |
| :--- | :--- | :--- |
| **Supplies & Inventory** | Stock levels & expiry | Add new supplies, track expiration dates, update quantities, search products, add items to cart, and generate issue/bill slips. |
| **Personnel Directory** | Emergency staff | Register responders, search personnel records by ID or name, and maintain staff profiles. |
| **Vehicle & Fleet** | Emergency vehicles | Track vehicle availability, allocate units for responses, and manage dispatch fleet inventory. |
| **Response Tracking** | Mission dispatch | Monitor emergency calls, verify response requests, record approvals, and view hotline directories. |

---

## System Workflow

1. **Authentication**: Sign in with administrative credentials on the login screen.
2. **Central Dashboard**: Access all major subsystems—Supplies, Personnel, Vehicles, and Response Tracking—from the main menu.
3. **Cart & Dispatch Allocation**: Select supplies and vehicles needed for a specific response run, review allocations in the cart, and confirm dispatch.
4. **Automatic Stock Update**: Inventory counts are automatically adjusted in MySQL upon checkout/approval.
5. **Emergency Hotlines**: Built-in speed dial and directory for quick crisis communication.

---

## Project Structure & Files

- [`Login.java`](src/MainFiles/Login.java): Authentication window and validation.
- [`mainmenu.java`](src/MainFiles/mainmenu.java): Central navigation dashboard.
- [`supplies.java`](src/MainFiles/supplies.java): Supplies inventory table and stock management.
- [`Searchproduct.java`](src/MainFiles/Searchproduct.java): Real-time product search and stock lookup.
- [`cartpersonnel.java`](src/MainFiles/cartpersonnel.java) / [`billper.java`](src/MainFiles/billper.java): Item cart allocation, billing, and inventory deduction.
- [`Register.java`](src/MainFiles/Register.java) / [`Personnel.java`](src/MainFiles/Personnel.java): Responder registration and personnel directory.
- [`vehicle.java`](src/MainFiles/vehicle.java) / [`vecart.java`](src/MainFiles/vecart.java): Fleet management and vehicle cart allocations.
- [`Track.java`](src/MainFiles/Track.java) / [`approve.java`](src/MainFiles/approve.java): Response dispatch tracking and request approvals.
- [`hotline.java`](src/MainFiles/hotline.java): Quick-access emergency hotline directory.

---

## License

[The Unlicense](LICENSE). Free and unencumbered software released into the public domain.