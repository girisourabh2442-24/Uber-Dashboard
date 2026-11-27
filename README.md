# Uber-Dashboard
End-to-end Power BI &amp; SQL analysis of ~150K Uber ride bookings covering demand trends, vehicle performance, cancellation drivers, and payment behavior.
# Uber Ride Bookings — Power BI & SQL Analytics Dashboard

An interactive Power BI dashboard and SQL verification project analyzing **~150K Uber ride bookings** to uncover trends in ride demand, booking value, vehicle performance, cancellations, and payment behavior.

<img width="1535" height="862" alt="Dash1-Home" src="https://github.com/user-attachments/assets/b8630c45-3f5b-4f04-8177-13beaf6fa375" />

## 📌 Overview

The report has three pages:

| Page | What It Shows |
| :--- | :--- |
| **Home** | Landing page with project overview and custom navigation buttons |
| **Overview** | Ride volume, distance, completed vs. lost bookings, booking value trends, and vehicle-type performance |
| **Booking & Operational Analysis** | Customer metrics, success and cancellation rates, booking status breakdown, and payment methods |

---

## 📸 Screenshots

<img width="1535" height="862" alt="Dash2-Overview" src="https://github.com/user-attachments/assets/532b3f4c-ee8b-47aa-aab3-c141f7c5694e" />


<img width="1535" height="862" alt="Dash3-booing and operations" src="https://github.com/user-attachments/assets/2839fe02-5f6b-44ac-94ce-72f1dc830939" />

## ✨ Features

* **KPI Cards:** Total distance, booking count, average distance, completed bookings, lost bookings, total customers, successful booking rate, cancellation rate, and average booking value
* **Time Trends:** Completed bookings and booking value over time, with a **Month / Quarter** toggle
* **Vehicle Analysis:** Booking value by vehicle type (**Auto, Go Mini, Go Sedan, Bike, Premier Sedan, eBike, Uber XL**)
* **Booking Status Breakdown:** Completed, Cancelled by Driver, Cancelled by Customer, No Driver Found, Incomplete
* **Payment Mix:** UPI, Cash, Uber Wallet, Credit Card, Debit Card
* **Ratings:** Driver rating count and average customer rating
* **Page Navigation:** Custom page navigation buttons and a vehicle selector panel

---

## 🔍 Key Insights

* **Completion vs. Cancellations:** **62%** of bookings were completed (**93K of 150K**), while **25%** were cancelled.
* **Cancellation Drivers:** Driver cancellations (**18%**) are the biggest cause of lost bookings—more than double customer cancellations (**7%**).
* **Vehicle Performance:** **Auto** generates the highest booking value (**₹12.9M**), followed by **Go Mini** (**₹10.3M**) and **Go Sedan** (**₹9.4M**). **Uber XL** is the lowest (**₹1.5M**).
* **Booking Value:** Total booking value is approximately **₹52M**, with an average booking value of **₹508.30**.
* **Ratings & Demand:** Average customer rating is **4.40 / 5**, and daily completed bookings stay fairly steady with one clear demand spike around the third week of the period.

---

## 🛠️ Tech Stack

| Area | Tools |
| :--- | :--- |
| **Visualization** | Microsoft Power BI Desktop |
| **Data Modeling & Measures** | Power Query, DAX |
| **KPI Cross-Verification** | SQL (`sql/kpi_verification.sql`) |
| **Data Source** | Uber ride bookings dataset (CSV) |

---

## 📂 Project Structure

```text
Uber-Ride-Bookings-PowerBI-SQL-Analysis/
├── data/                                # Uber ride bookings dataset (CSV)
├── docs/                                # DAX measures & data model documentation
├── images/                              # Dashboard screenshots (01_home.png, 02_overview.png, 03_booking_operations.png)
├── sql/                                 # SQL KPI verification queries
├── dashboard/
│   └── uber_bookings_dashboard.pbix     # Power BI report file
├── .gitignore
├── LICENSE
└── README.md

DAX Measures
Code snippet
Average Booking Value = 
AVERAGE(Uber[Booking Value])

Average Distance = 
AVERAGE(Uber[Ride Distance])

Booking Count = 
DISTINCTCOUNT(Uber[Booking ID])

Booking_Value = 
SUM(Uber[Booking Value])

Cancellation Rate (%) = 
DIVIDE(
    CALCULATE(
        COUNTROWS(Uber),
        Uber[Booking Status] IN {
            "Cancelled by Driver",
            "Cancelled by Customer"
        }
    ),
    COUNTROWS(Uber),
    0
)

Completed Bookings = 
CALCULATE([Booking Count], Uber[Booking Status] = "Completed")

Lost Bookings = 
CALCULATE([Booking Count], Uber[Booking Status] <> "Completed")

Successful Booking Rate = 
DIVIDE(
    CALCULATE(
        COUNTROWS(Uber),
        Uber[Booking Status] = "Completed"
    ),
    COUNTROWS(Uber),
    0
)

Total Customer = 
DISTINCTCOUNT(Uber[Customer ID])

Total Distance = 
SUM(Uber[Ride Distance])

Future Improvements
Add a map visual for pickup and drop-off hotspots

Add demand forecasting

Connect to a live data source for automatic refresh

Add driver-level performance analysis

Contact
Sourabh Ganesh Giri

LINKEDIN- https://www.linkedin.com/in/sourabh-giri-data-analyst/
GITHUB-https://github.com/girisourabh2442-24/Brazilian-Ecommerce-PowerBI-SQL-Analysis
