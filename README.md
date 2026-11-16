# Rriwaaz 👗

![Project Status](https://img.shields.io/badge/status-%20production-green)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

> **"Elegance Stitched to Perfection."**
> A dedicated platform for custom ladies' tailoring, ethnic wear, and boutique services.

## 📖 About The Project

**Rriwaaz** is a web application designed to digitize the traditional ladies' tailoring experience. It allows users to browse trending designs (Suits, Lehengas, Blouses), book custom stitching services, and manage their measurements online.

This project is a specialized iteration of a previous tailoring platform, optimized specifically for women's fashion requirements and boutique management.

### ✨ Key Features

* **Design Gallery:** Browse latest trends in ethnic and western wear.
* **Custom Stitching Orders:** Users can select styles (neck designs, sleeve types) and place orders.
* **Measurement Profile:** specific inputs for ladies' garment fitting (Kurti length, bust, waist, hip, bottom length, etc.).
* **Appointment Booking:** Schedule visits for measurements or trials.
* **Order Tracking:** Live status updates (Fabric Received, Cutting, Stitching, Ready).
* **Admin Dashboard:** For managing fabric inventory, orders, and customer data.

---

## 🛠️ Tech Stack

Built using the **MERN Stack** with **Tailwind CSS** for styling.

* **Frontend:** React.js, Tailwind CSS, Framer Motion (for animations).
* **Backend:** Node.js, Express.js.
* **Database:** MongoDB (Schemas optimized for complex measurement data).
* **Authentication:** JWT (JSON Web Tokens).
* **State Management:** Context API / Redux.

---

## 🚀 Getting Started

### Prerequisites

* Node.js installed
* MongoDB URI ready

### Installation

1.  **Clone the Repo**
    ```bash
    git clone [https://github.com/yourusername/rriwaaz.git](https://github.com/yourusername/rriwaaz.git)
    cd rriwaaz
    ```

2.  **Install Dependencies**
    ```bash
    # Install server dependencies
    cd server
    npm install

    # Install client dependencies
    cd ../client
    npm install
    ```

3.  **Configure Environment**
    Create a `.env` file in the `server` folder:
    ```env
    PORT=5000
    MONGO_URI=your_mongodb_connection_string
    JWT_SECRET=your_secret_key
    ```

4.  **Run the App**
    ```bash
    # Run Backend (from server folder)
    npm run dev

    # Run Frontend (from client folder)
    npm run dev
    ```

---

## 📂 Database Schema Overview (Key Differences)

Since this is focused on ladies' wear, the `Order` schema includes specific style preferences:

```javascript
const OrderSchema = new mongoose.Schema({
  customer: { type: ObjectId, ref: 'User' },
  garmentType: { type: String, enum: ['Suit', 'Lehenga', 'Blouse', 'Gown'] },
  measurements: {
    bust: Number,
    waist: Number,
    hip: Number,
    kameezLength: Number,
    salwarLength: Number,
  },
  designPreferences: {
    neckDesign: String,
    sleeveLength: String,
    notes: String
  },
  status: { type: String, default: 'Pending' }
});