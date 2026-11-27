# Uber Ride Bookings — Power BI & SQL Analytics Dashboard

An interactive Power BI dashboard and SQL verification project analyzing **~150K Uber ride bookings** to uncover trends in ride demand, booking value, vehicle performance, cancellations, and payment behavior.

<img width="1535" height="862" alt="Dash1-Home" src="https://github.com/user-attachments/assets/90c2397c-78f1-4f7f-85b1-5b2c53f9d9f2" />


## 📌 Overview
The report has three pages:

| Page | What It Shows |
| :--- | :--- |
| **Home** | Landing page with project overview and custom navigation buttons |
| **Overview** | Ride volume, distance, completed vs. lost bookings, booking value trends, and vehicle-type performance |
| **Booking & Operational Analysis** | Customer metrics, success and cancellation rates, booking status breakdown, and payment methods |

## 📸 Screenshots

<img width="1535" height="862" alt="Dash2-Overview" src="https://github.com/user-attachments/assets/114f0d9f-486a-4d2a-850a-64ccfd6a58b6" />

<img width="1535" height="862" alt="Dash3-booing and operations" src="https://github.com/user-attachments/assets/f4ae980a-db54-4414-a492-8c3f2ed17955" />

## ✨ Features
- **KPI Cards:** Total distance, booking count, average distance, completed bookings, lost bookings, total customers, successful booking rate, cancellation rate, and average booking value
- **Time Trends:** Completed bookings and booking value over time, with a **Month / Quarter** toggle
- **Vehicle Analysis:** Booking value by vehicle type (*Auto, Go Mini, Go Sedan, Bike, Premier Sedan, eBike, Uber XL*)
- **Booking Status Breakdown:** Completed, Cancelled by Driver, Cancelled by Customer, No Driver Found, Incomplete
- **Payment Mix:** UPI, Cash, Uber Wallet, Credit Card, Debit Card
- **Ratings:** Driver rating count and average customer rating
- **Page Navigation:** Custom page navigation buttons and a vehicle selector panel

## 🔍 Key Insights
- **Completion vs. Cancellations:** **62%** of bookings were completed (**93K of 150K**), **25%** were cancelled, and the remaining **13%** resulted in *No Driver Found* or *Incomplete* rides (making total non-completed / lost bookings **38%**).
- **Cancellation Drivers:** Driver cancellations (**18%**) are the biggest cause of lost bookings—more than double customer cancellations (**7%**).
- **Vehicle Performance:** **Auto** generates the highest booking value (**₹12.9M**), followed by **Go Mini** (**₹10.3M**) and **Go Sedan** (**₹9.4M**). **Uber XL** is the lowest (**₹1.5M**).
- **Booking Value:** Total booking value is approximately **₹52M**, with an average booking value of **₹508.30**.
- **Ratings & Demand:** Average customer rating is **4.40 / 5**, and daily completed bookings stay fairly steady with one clear demand spike around the third week of the period.

## 🛠️ Tech Stack
| Area | Tools |
| :--- | :--- |
| **Visualization** | Microsoft Power BI Desktop |
| **Data Modeling & Measures** | Power Query, DAX |
| **KPI Cross-Verification** | SQL (`sql/kpi_verification.sql`) |
| **Data Source** | Uber ride bookings dataset (CSV) |

## 📂 Project Structure
```text
Uber-Dashboard/
├── data/                                # Uber ride bookings dataset (CSV)
├── docs/                                # DAX measures & data model documentation
├── images/                              # Dashboard screenshots (01_home.png, 02_overview.png, 03_booking_operations.png)
├── sql/                                 # SQL KPI verification queries
│   └── kpi_verification.sql
├── dashboard/
│   └── uber_bookings_dashboard.pbix     # Power BI report file
├── .gitignore
├── LICENSE
└── README.md



