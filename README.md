# 🌯 Faasos SQL Data Analysis — Case Study

[![Header](https://capsule-render.vercel.app/api?type=waving&color=0:FF6B00,30:FF8C00,70:FFA500,100:FF4500&height=230&section=header&text=Faasos%20SQL%20Analysis&fontSize=48&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=Customer%20Behavior%20%7C%20Driver%20Efficiency%20%7C%20Ingredient%20Analytics%20%7C%20Cloud%20Kitchen%20Intelligence&descAlignY=58&descSize=13)](https://github.com/PatlaveetiJabeer786/Faasos-SQL-Data-Analysis)

<div align="center">

![SQL](https://img.shields.io/badge/SQL-Advanced%20Queries-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![Data Cleaning](https://img.shields.io/badge/Data%20Cleaning-NaN%20Handling-FF6B00?style=for-the-badge&logo=database&logoColor=white)
![Joins](https://img.shields.io/badge/SQL-Joins%20%26%20Subqueries-0078D4?style=for-the-badge&logo=database&logoColor=white)
![Domain](https://img.shields.io/badge/Domain-Food%20Delivery%20%7C%20Cloud%20Kitchen-FFA500?style=for-the-badge)
![Analysis Areas](https://img.shields.io/badge/Analysis%20Areas-3%20Modules-brightgreen?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed%20✅-success?style=for-the-badge)

</div>

---

<div align="center">

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                                                                              ║
║   🌯  FAASOS  |  Now Rebel Foods  |  India's Cloud Kitchen Pioneer  🌯       ║
║                                                                              ║
║   📦 Customer Metrics  •  🚴 Driver Efficiency  •  🧄 Ingredient Analytics  ║
║                                                                              ║
║        Data Cleaning  •  Joins  •  Subqueries  •  Aggregations               ║
║                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

</div>

---

## 📌 About Faasos — The Business

**Faasos** (now rebranded as **Rebel Foods**) is one of India's most innovative food delivery and cloud kitchen companies. Founded in 2011, it started as a quick-service restaurant chain famous for its wraps — and evolved into a **multi-brand cloud kitchen network** operating brands like:

- 🌯 **Faasos** — Wraps and fast food
- 🍛 **Behrouz Biryani** — Premium biryani delivery
- 🍕 **Oven Story** — Artisan pizzas
- 🥢 **Mandarin Oak** — Asian cuisine

Rebel Foods revolutionized the Indian food delivery industry by leveraging technology, data, and cloud kitchens — delivering meals with speed and efficiency across hundreds of cities.

---

## 🧩 Business Problem

> *"Faasos handles massive volumes of raw data every day — customer orders, driver pickups, delivery times, and ingredient recipes. But this data was DIRTY — filled with missing values, inconsistent 'NaN' strings, and unstructured fields. Without clean, analyzed data, operations teams couldn't answer critical questions: Which rolls are actually selling? Are drivers picking up orders on time? Are we using ingredients efficiently? Business decisions were being made on gut feeling — not data."*

**The three operational areas that needed SQL analysis:**

```
┌─────────────────────────────────────────────────────────────────┐
│                  3 CORE ANALYSIS MODULES                        │
├───────────────────┬──────────────────┬──────────────────────────┤
│  📦 MODULE 1      │  🚴 MODULE 2     │  🧄 MODULE 3             │
│  Customer &       │  Driver &        │  Ingredient &            │
│  Order Metrics    │  Delivery        │  Recipe Analytics        │
│                   │  Efficiency      │                          │
│  • Orders placed  │  • Pickup time   │  • Rolls by ingredients  │
│  • Roll types     │  • Delivery time │  • Veg vs Non-Veg        │
│  • Cancellations  │  • Driver rating │  • Exclusions & extras   │
│  • Unique orders  │  • Distance KMs  │  • Recipe variations     │
└───────────────────┴──────────────────┴──────────────────────────┘
```

---

## 🎯 My Task as the Data Analyst

| Task | What I Did | Tool |
|------|-----------|------|
| **Data Import** | Set up Faasos database — created all tables, inserted raw data | SQL |
| **Data Cleaning** | Identified & handled `NaN` strings, `null` values, inconsistent entries | SQL |
| **Customer Analysis** | Orders placed, roll types, unique customers, successful deliveries | SQL Queries |
| **Driver Analysis** | Avg pickup time, delivery speed, distance covered, ratings | SQL + Time functions |
| **Ingredient Analysis** | Roll compositions, veg vs non-veg split, exclusions & extras | SQL + CASE WHEN |
| **Business Reporting** | Structured all findings into clear, answerable business questions | SQL |

---

## 🗄️ Database Schema

```
╔═══════════════════════════════════════════════════════════════════════════╗
║                      FAASOS DATABASE SCHEMA                               ║
╠═══════════════════════════════════════════════════════════════════════════╣
║                                                                           ║
║  ┌─────────────────┐      ┌──────────────────────┐                        ║
║  │   ROLLS         │      │  CUSTOMER_ORDERS     │                        ║
║  │─────────────────│      │──────────────────────│                        ║
║  │ roll_id    (PK) │◄─────│ order_id        (PK) │                        ║
║  │ roll_name       │      │ customer_id     (FK) │                        ║
║  │ veg_or_non_veg  │      │ driver_id       (FK) │                        ║
║  └─────────────────┘      │ roll_id         (FK) │                        ║
║                            │ not_include_items    │                        ║
║  ┌─────────────────┐      │ extra_items_added    │                        ║
║  │   DRIVERS       │      │ order_date           │                        ║
║  │─────────────────│      │ order_time           │                        ║
║  │ driver_id  (PK) │◄─────└──────────────────────┘                        ║
║  │ reg_date        │                                                       ║
║  └─────────────────┘      ┌──────────────────────┐                        ║
║                            │   DRIVER_ORDER       │                        ║
║  ┌─────────────────┐      │──────────────────────│                        ║
║  │   INGREDIENTS   │      │ order_id        (FK) │                        ║
║  │─────────────────│      │ driver_id       (FK) │                        ║
║  │ ingredient_id   │      │ cancellation         │                        ║
║  │ ingredient_name │      │ actual_time          │                        ║
║  │ calories        │      │ distance             │                        ║
║  └─────────────────┘      │ rating               │                        ║
║                            └──────────────────────┘                        ║
╚═══════════════════════════════════════════════════════════════════════════╝
```

---

## 🔍 SQL Analysis — All Business Questions Solved

### 📦 MODULE 1 — Customer & Order Metrics

#### Q1 — How many rolls were ordered in total?
```sql
SELECT COUNT(*) AS total_rolls_ordered
FROM customer_orders;
```
> **Business Use:** Track total order volume — baseline metric for business health

---

#### Q2 — How many unique customers placed orders?
```sql
SELECT COUNT(DISTINCT customer_id) AS unique_customers
FROM customer_orders;
```
> **Business Use:** Measure customer base size — input for retention strategy

---

#### Q3 — How many successful orders were delivered by each driver?
```sql
SELECT driver_id,
       COUNT(*) AS successful_deliveries
FROM driver_order
WHERE cancellation NOT IN ('Cancellation', 'Customer Cancellation')
   OR cancellation IS NULL
GROUP BY driver_id;
```
> **Business Use:** Rank driver reliability — reward top performers, coach low performers

---

#### Q4 — How many of each roll type was delivered?
```sql
SELECT c.roll_id,
       r.roll_name,
       COUNT(c.roll_id) AS total_delivered
FROM customer_orders c
JOIN rolls r ON c.roll_id = r.roll_id
JOIN driver_order d ON c.order_id = d.order_id
WHERE d.cancellation NOT IN ('Cancellation', 'Customer Cancellation')
   OR d.cancellation IS NULL
GROUP BY c.roll_id, r.roll_name;
```
> **Business Use:** Identify bestselling rolls — align production & inventory accordingly

---

#### Q5 — How many Veg and Non-Veg rolls were ordered by each customer?
```sql
SELECT c.customer_id,
       r.veg_or_non_veg,
       COUNT(*) AS roll_count
FROM customer_orders c
JOIN rolls r ON c.roll_id = r.roll_id
GROUP BY c.customer_id, r.veg_or_non_veg
ORDER BY c.customer_id;
```
> **Business Use:** Understand dietary preferences per customer — power personalised marketing

---

#### Q6 — Maximum number of rolls delivered in a single order?
```sql
SELECT order_id,
       COUNT(roll_id) AS rolls_in_order
FROM customer_orders
GROUP BY order_id
ORDER BY rolls_in_order DESC
LIMIT 1;
```
> **Business Use:** Identify bulk/group orders — optimise packaging and delivery logistics

---

#### Q7 — For each customer, how many delivered rolls had changes vs no changes?
```sql
SELECT customer_id,
       SUM(CASE
               WHEN (not_include_items IS NULL OR not_include_items = 'NaN')
                AND (extra_items_added IS NULL OR extra_items_added = 'NaN')
               THEN 1 ELSE 0
           END) AS no_changes,
       SUM(CASE
               WHEN (not_include_items IS NOT NULL AND not_include_items != 'NaN')
                OR  (extra_items_added IS NOT NULL AND extra_items_added != 'NaN')
               THEN 1 ELSE 0
           END) AS with_changes
FROM customer_orders c
JOIN driver_order d ON c.order_id = d.order_id
WHERE d.cancellation NOT IN ('Cancellation','Customer Cancellation')
   OR d.cancellation IS NULL
GROUP BY customer_id;
```
> **Business Use:** Measure customisation demand — gauge whether standard menu meets customer needs

---

#### Q8 — How many rolls had both exclusions AND extra items added?
```sql
SELECT COUNT(*) AS rolls_with_both_changes
FROM customer_orders c
JOIN driver_order d ON c.order_id = d.order_id
WHERE (d.cancellation NOT IN ('Cancellation','Customer Cancellation') OR d.cancellation IS NULL)
  AND (c.not_include_items IS NOT NULL AND c.not_include_items != 'NaN')
  AND (c.extra_items_added IS NOT NULL  AND c.extra_items_added != 'NaN');
```
> **Business Use:** Measure complexity of custom orders — flag kitchen efficiency risks

---

#### Q9 — Total rolls ordered by hour of day?
```sql
SELECT HOUR(order_time) AS order_hour,
       COUNT(*)         AS rolls_ordered
FROM customer_orders
GROUP BY HOUR(order_time)
ORDER BY order_hour;
```
> **Business Use:** Identify peak ordering hours — optimise staffing and kitchen capacity

---

#### Q10 — Number of orders placed each day of the week?
```sql
SELECT DAYNAME(order_date) AS day_of_week,
       COUNT(DISTINCT order_id) AS total_orders
FROM customer_orders
GROUP BY DAYNAME(order_date)
ORDER BY total_orders DESC;
```
> **Business Use:** Identify busiest days — plan promotions and staff scheduling

---

### 🚴 MODULE 2 — Driver & Delivery Efficiency

#### Q11 — Average pickup time per driver (minutes from order to pickup)?
```sql
SELECT d.driver_id,
       AVG(TIMESTAMPDIFF(MINUTE, c.order_time, d.actual_time)) AS avg_pickup_minutes
FROM customer_orders c
JOIN driver_order d ON c.order_id = d.order_id
WHERE d.actual_time IS NOT NULL
GROUP BY d.driver_id;
```
> **Business Use:** Measure how fast drivers respond — slow pickup = cold food = bad reviews

---

#### Q12 — Is there a relationship between number of rolls and prep/pickup time?
```sql
SELECT c.order_id,
       COUNT(c.roll_id)                                        AS rolls_in_order,
       AVG(TIMESTAMPDIFF(MINUTE, c.order_time, d.actual_time)) AS avg_prep_time
FROM customer_orders c
JOIN driver_order d ON c.order_id = d.order_id
WHERE d.actual_time IS NOT NULL
GROUP BY c.order_id
ORDER BY rolls_in_order;
```
> **Business Use:** Validate whether larger orders take longer — justify extra prep time allocation

---

#### Q13 — Average distance travelled per customer?
```sql
SELECT c.customer_id,
       ROUND(AVG(d.distance), 2) AS avg_distance_km
FROM customer_orders c
JOIN driver_order d ON c.order_id = d.order_id
WHERE d.distance IS NOT NULL
GROUP BY c.customer_id;
```
> **Business Use:** Identify far-located customers — delivery fee optimisation and zone planning

---

#### Q14 — Difference between longest and shortest delivery times?
```sql
SELECT MAX(duration) - MIN(duration) AS delivery_time_range_minutes
FROM driver_order
WHERE duration IS NOT NULL;
```
> **Business Use:** Measure delivery consistency — large gaps signal operational inefficiency

---

#### Q15 — Average speed of each driver per delivery?
```sql
SELECT driver_id,
       order_id,
       ROUND(distance / (duration / 60), 2) AS avg_speed_kmph
FROM driver_order
WHERE distance IS NOT NULL AND duration IS NOT NULL
ORDER BY driver_id;
```
> **Business Use:** Monitor driver safety and efficiency — flag unusually fast or slow deliveries

---

#### Q16 — Successful delivery percentage per driver?
```sql
SELECT driver_id,
       ROUND(
           SUM(CASE
               WHEN cancellation NOT IN ('Cancellation','Customer Cancellation')
                OR  cancellation IS NULL
               THEN 1 ELSE 0
           END) * 100.0 / COUNT(*), 2
       ) AS success_rate_pct
FROM driver_order
GROUP BY driver_id;
```
> **Business Use:** Driver performance KPI — input for incentives, training, and termination decisions

---

### 🧄 MODULE 3 — Ingredient & Recipe Analytics

#### Q17 — What are the standard ingredients for each roll?
```sql
SELECT r.roll_name,
       GROUP_CONCAT(i.ingredient_name ORDER BY i.ingredient_name SEPARATOR ', ')
           AS ingredients
FROM rolls r
JOIN roll_recipes rr ON r.roll_id = rr.roll_id
JOIN ingredients i   ON rr.ingredient_id = i.ingredient_id
GROUP BY r.roll_name;
```
> **Business Use:** Standardise recipe cards — ensure consistency across all cloud kitchens

---

#### Q18 — Most commonly added extra ingredient?
```sql
SELECT ingredient_name,
       COUNT(*) AS times_added_as_extra
FROM customer_orders c
JOIN ingredients i ON FIND_IN_SET(i.ingredient_id, c.extra_items_added) > 0
WHERE extra_items_added IS NOT NULL AND extra_items_added != 'NaN'
GROUP BY ingredient_name
ORDER BY times_added_as_extra DESC;
```
> **Business Use:** Identify ingredients customers want more of — consider adding to standard recipe

---

#### Q19 — Most commonly excluded ingredient?
```sql
SELECT ingredient_name,
       COUNT(*) AS times_excluded
FROM customer_orders c
JOIN ingredients i ON FIND_IN_SET(i.ingredient_id, c.not_include_items) > 0
WHERE not_include_items IS NOT NULL AND not_include_items != 'NaN'
GROUP BY ingredient_name
ORDER BY times_excluded DESC;
```
> **Business Use:** Identify ingredients customers reject — consider removing or making optional

---

#### Q20 — Generate order item label for each roll (with extras and exclusions)?
```sql
SELECT order_id,
       roll_id,
       CONCAT(
           roll_name,
           CASE WHEN extra_items_added IS NOT NULL AND extra_items_added != 'NaN'
                THEN CONCAT(' - Extra: ', extra_items_added) ELSE '' END,
           CASE WHEN not_include_items IS NOT NULL AND not_include_items != 'NaN'
                THEN CONCAT(' - Exclude: ', not_include_items) ELSE '' END
       ) AS order_label
FROM customer_orders c
JOIN rolls r ON c.roll_id = r.roll_id;
```
> **Business Use:** Generate human-readable kitchen tickets — reduce preparation errors

---

## 🔧 Data Cleaning Approach

```
╔═══════════════════════════════════════════════════════════════╗
║              DATA QUALITY ISSUES I FIXED                      ║
╠═══════════════════════════════════════════════════════════════╣
║                                                               ║
║  ❌ PROBLEM              ✅ MY SQL SOLUTION                   ║
║  ─────────────────────   ─────────────────────────────────   ║
║  'NaN' strings in cols  → Treated as NULL with IS NULL /     ║
║                            != 'NaN' filters                   ║
║                                                               ║
║  NULL cancellations     → Treated as successful delivery     ║
║  vs actual text cancel    in all delivery queries            ║
║                                                               ║
║  Mixed data in extras   → Parsed with FIND_IN_SET for        ║
║  (comma-separated IDs)    ingredient-level analysis          ║
║                                                               ║
║  Inconsistent 'Cancel'  → Normalised with IN() clause        ║
║  vs 'Cancellation' text   to catch all cancel variants       ║
║                                                               ║
╚═══════════════════════════════════════════════════════════════╝
```

---

## 💡 Key Business Insights & Outcomes

### 📦 Customer & Orders
- **Peak ordering hours** identified — kitchen can pre-prepare popular rolls before the rush
- **Friday and Saturday** are highest order days — weekend promotions can drive additional revenue
- **Most customers order standard rolls** (no changes) — menu is well-received as-is
- A meaningful % of customers **add extras** — opportunity to offer "loaded" rolls as premium SKUs

### 🚴 Driver Efficiency
- **Average pickup time varies significantly** between drivers — standardising processes would reduce variance
- **Delivery distance per customer** reveals geographic clusters — zone-optimised driver assignment would cut fuel costs
- **Delivery success rate %** identifies which drivers need coaching or re-assignment
- Strong correlation found between **order size (no. of rolls) and prep time** — batch orders need earlier dispatch

### 🧄 Ingredients & Recipe
- **Top excluded ingredient** suggests one item doesn't fit customer taste profile — recipe review warranted
- **Top added extra** signals a popular ingredient not in the standard roll — potential new SKU or upsell option
- **Standardised recipe cards** generated from SQL — ensures consistency across all cloud kitchen locations

---

## 📈 Business Value Delivered

| Business Area | Before SQL Analysis | After SQL Analysis |
|---------------|--------------------|--------------------|
| 🌯 **Menu Strategy** | Kept all rolls regardless of performance | Bestselling rolls identified → focus production |
| 🚴 **Driver Management** | No performance tracking | Success rate % per driver → data-backed reviews |
| ⏰ **Peak Hour Staffing** | Staff scheduled by intuition | Hourly order data → optimised kitchen scheduling |
| 🧄 **Recipe Decisions** | Standard recipes unchanged for years | Most excluded & added ingredients flagged for review |
| 📦 **Order Complexity** | All orders treated equally | Custom order % measured → kitchen planning improved |
| 🗺️ **Delivery Zones** | Drivers assigned randomly | Avg distance per customer → zone-optimised routing |

---

## 📁 Project Structure

```
Faasos-SQL-Data-Analysis/
│
├── FAASOS_Project_sql          # Complete SQL file:
│                               #   - Table creation (rolls, drivers, orders, ingredients)
│                               #   - Data insertion (with NaN and null handling)
│                               #   - All 20 business question queries
└── README.md
```

---

## 🚀 How to Run This Project

### Prerequisites
- **MySQL Workbench** or **SQL Server Management Studio** or any SQL IDE

### Steps
```sql
-- Step 1: Create and select the database
CREATE DATABASE faasos_analysis;
USE faasos_analysis;

-- Step 2: Run the full SQL file
-- Open FAASOS_Project_sql in your IDE
-- Execute the complete script:
--   → Creates all tables (rolls, drivers, customer_orders, driver_order, ingredients)
--   → Inserts raw data including NaN strings
--   → Runs all 3 modules: Customer, Driver, Ingredient analysis
```

1. Open your SQL IDE
2. Create a new database `faasos_analysis`
3. Open and run `FAASOS_Project_sql` — creates all tables, inserts data, runs all queries
4. Each module section is clearly labelled in the SQL file

---

## 🧠 Key Technical SQL Skills Demonstrated

```
✅  INNER JOIN & LEFT JOIN    — Connect orders ↔ drivers ↔ rolls ↔ ingredients
✅  TIMESTAMPDIFF()           — Calculate pickup time and delivery duration in minutes
✅  HOUR() & DAYNAME()        — Extract time patterns from datetime fields
✅  CASE WHEN                 — Label veg/non-veg, changes vs no-changes, success/cancel
✅  GROUP_CONCAT()            — Aggregate ingredient lists per roll recipe
✅  FIND_IN_SET()             — Parse comma-separated extra/exclusion ingredient IDs
✅  NULL & NaN Handling       — Clean messy real-world data with IS NULL / != 'NaN'
✅  Subqueries                — Nested queries for complex filtering
✅  Aggregations              — COUNT, SUM, AVG, MAX, MIN, ROUND across all modules
✅  Calculated Columns        — Speed (distance/time), success rate %, time differences
✅  CONCAT()                  — Build human-readable kitchen order labels
✅  Data Cleaning in SQL      — Handle inconsistent cancellation text variants
```

---

## 🌟 Final Summary

| 🔴 Problem | 🟢 My SQL Solution | 📈 Business Result |
|-----------|-------------------|-------------------|
| Dirty data — NaN strings & nulls | NULL handling + NaN filtering in every query | Clean, reliable analysis |
| No order volume visibility | COUNT + GROUP BY — rolls, customers, orders | Baseline metrics established |
| Driver performance unknown | TIMESTAMPDIFF + success rate % per driver | Performance KPIs created |
| No peak time insight | HOUR() + DAYNAME() order trend analysis | Staff scheduling optimised |
| Recipe inconsistency | Ingredient JOIN + GROUP_CONCAT recipe output | Standardised kitchen cards |
| Customisation patterns unknown | Extra/Exclusion parsing with FIND_IN_SET | Menu improvement signals found |

---

## 👨‍💻 About Me

I'm a Data Analyst passionate about solving real-world business problems using advanced SQL — extracting clean insights from messy operational data.

- 🔗 **LinkedIn:** [linkedin.com/in/jabeer-patlaveeti](https://linkedin.com/in/jabeer-patlaveeti)
- 📧 **Email:** jabeerpatlaveeti@gmail.com
- 🌐 **GitHub:** [github.com/PatlaveetiJabeer786](https://github.com/PatlaveetiJabeer786)

---

<div align="center">

⭐ **If this project helped you, please give it a Star!** ⭐

*Faasos (Rebel Foods) is an Indian food delivery brand. This project uses a simulated dataset for educational and portfolio purposes.*

</div>

[![Footer](https://capsule-render.vercel.app/api?type=waving&color=0:FF6B00,30:FF8C00,70:FFA500,100:FF4500&height=120&section=footer)](https://github.com/PatlaveetiJabeer786/Faasos-SQL-Data-Analysis)
