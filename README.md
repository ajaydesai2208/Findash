# Findash: Your Personal Financial Dashboard

This project is a full-stack financial dashboard application designed to visualize key financial metrics, product performance, and transaction data. It provides an intuitive interface for tracking revenue, expenses, and profit, along with predictive analytics based on historical data.

This application serves as a foundation for my personal finance tracking and demonstrates my proficiency in modern web development technologies.

## Features

* **Dashboard Overview:** Comprehensive visualization of financial KPIs (Key Performance Indicators) including total profit, revenue, and expenses.

* **Monthly and Daily Data:** Detailed breakdown of financial performance over time.

* **Expense Breakdown:** Categorization of expenses for better financial insights.

* **Product Performance:** Listing of products with their prices, expenses, and associated transactions.

* **Recent Transactions:** A view of the latest financial transactions.

* **Predictions:** Utilizes linear regression to forecast future revenue based on historical trends.

* **Responsive Design:** Optimized for various screen sizes, from desktop to mobile.

## Technologies Used

This application is built using a modern MERN (MongoDB, Express.js, React, Node.js) stack, along with several other key libraries and tools:

**Frontend (Client):**

* **React:** A JavaScript library for building user interfaces.

* **TypeScript:** A typed superset of JavaScript that compiles to plain JavaScript.

* **Vite:** A fast build tool that provides a lightning-fast development experience.

* **Material-UI (MUI):** A comprehensive React UI library implementing Google's Material Design.

* **Redux Toolkit Query (RTK Query):** A powerful data fetching and caching tool built on Redux Toolkit, simplifying API interactions.

* **Recharts:** A composable charting library built on React components for data visualization.

* **React Router DOM:** For declarative routing within the single-page application.

* **Regression.js:** For performing linear regression calculations for predictions.

**Backend (Server):**

* **Node.js:** A JavaScript runtime built on Chrome's V8 JavaScript engine.

* **Express.js:** A fast, unopinionated, minimalist web framework for Node.js.

* **MongoDB:** A NoSQL document database for flexible data storage.

* **Mongoose:** An elegant MongoDB object modeling tool for Node.js.

* **Mongoose Currency:** A Mongoose plugin for handling currency types.

* **Dotenv:** For loading environment variables from a `.env` file.

* **Helmet:** Helps secure Express apps by setting various HTTP headers.

* **Morgan:** HTTP request logger middleware for Node.js.

* **CORS:** Middleware to enable Cross-Origin Resource Sharing.

## Getting Started

Follow these steps to get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

Before you begin, ensure you have the following installed:

* **Node.js & npm:** Download and install from [nodejs.org](https://nodejs.org/). `npm` comes bundled with Node.js.

* **Git:** Download and install from [git-scm.com](https://git-scm.com/).

* **MongoDB Atlas Account:** A free cloud-hosted MongoDB database. Sign up at [cloud.mongodb.com](https://cloud.mongodb.com/).

### Installation

1.  **Clone the repository:**

    ```bash
    git clone [https://github.com/ajaydesai2208/Findash.git](https://github.com/ajaydesai2208/Findash.git)
    cd Findash

    ```

2.  **Set up MongoDB Atlas:**

    * Create a new **Free Cluster** on MongoDB Atlas.

    * Configure **Network Access** to allow access from anywhere (for local development).

    * Create a **Database User** with a strong password (e.g., `findash_user`).

    * Get your **Connection String** (URI) from the "Connect your application" section.

3.  **Configure Backend Environment Variables:**

    * Navigate into the `server` directory:

        ```bash
        cd server

        ```

    * Create a new file named `.env` in the `server` directory.

    * Add your MongoDB connection string and the server port to this file:

        ```env
        MONGO_URL=mongodb+srv://<your_db_user>:<your_db_password>@cluster0.abcde.mongodb.net/?retryWrites=true&w=majority
        PORT=9000

        ```

        *(Replace `<your_db_user>` and `<your_db_password>` with your MongoDB Atlas credentials.)*

4.  **Install Backend Dependencies:**

    * In the `server` directory, install the required packages:

        ```bash
        npm install --legacy-peer-deps

        ```

5.  **Populate Database (One-time):**

    * Open `server/index.js`.

    * **Uncomment** the following lines (around line 30-33) to insert initial data:

        ```javascript
            // await mongoose.connection.db.dropDatabase(); // Optional: uncomment to clear existing data
            KPI.insertMany(kpis);
            Product.insertMany(products);
            Transaction.insertMany(transactions);

        ```

    * Save `server/index.js`.

    * Start the backend server:

        ```bash
        npm run dev

        ```

    * Once the server starts and you see `Server Port: 9000`, **immediately re-comment** those lines in `server/index.js` and save the file again to prevent duplicate data insertion on subsequent restarts.

6.  **Configure Frontend Environment Variables:**

    * Navigate back to the root of the `client` directory:

        ```bash
        cd ../client

        ```

    * Create a new file named `.env` in the `client` directory.

    * Add the backend API URL to this file:

        ```env
        VITE_BASE_URL=http://localhost:9000/

        ```

7.  **Install Frontend Dependencies:**

    * In the `client` directory, install the required packages:

        ```bash
        npm install

        ```

### Running the Application

1.  **Start the Backend Server:**

    * In your terminal, navigate to the `server` directory:

        ```bash
        cd server
        npm run dev

        ```

    * Ensure the server starts successfully on `Port: 9000`.

2.  **Start the Frontend Development Server:**

    * Open a **new** terminal window.

    * Navigate to the `client` directory:

        ```bash
        cd client
        npm run dev

        ```

    * The application will open in your default browser (usually `http://localhost:5173/`).


