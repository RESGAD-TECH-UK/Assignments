# SQL Query – Analyzing Trip Cancellation Rates

You have two tables:

### **Table 1: Trips**

| Column Name | Type    | Description |
|-------------|---------|-------------|
| id          | int     | Primary key. Each trip has a unique ID. |
| client_id   | int     | Refers to the user who requested the trip. |
| driver_id   | int     | Refers to the driver assigned to the trip. |
| city_id     | int     | The city where the trip was requested. |
| status      | enum    | One of: `'completed'`, `'cancelled_by_driver'`, `'cancelled_by_client'`. |
| request_at  | varchar | The date the trip was requested (format: `YYYY-MM-DD`). |



### **Table 2: Users**

| Column Name | Type | Description |
|-------------|------|-------------|
| users_id    | int  | Primary key. Each user (client or driver) has a unique ID. |
| banned      | enum | Either `'Yes'` or `'No'`. Indicates if a user is banned. |
| role        | enum | One of: `'client'`, `'driver'`, `'partner'`. |



##  Your Task:
Write a SQL query that **computes the cancellation rate** of trips for each day **from `2013-10-01` to `2013-10-03`**, using only trips where **both the client and the driver are not banned**.

###  Cancellation Rate Formula:

Cancellation Rate = (Number of cancelled trips) / (Total trips)


Where:
- A cancelled trip has `status = 'cancelled_by_client'` or `'cancelled_by_driver'`
- A trip should be included **only if** both the `client` and the `driver` are **not banned**

---

## Requirements:

1. Only consider trips between `'2013-10-01'` and `'2013-10-03'`.
2. Group the results by day.
3. Round the cancellation rate to **two decimal places**.
4. Name the output columns as:
   - `Day` (the trip date)
   - `Cancellation Rate` (the computed rate)


## Expected Output Format:

| Day        | Cancellation Rate |
|------------|-------------------|
| 2013-10-01 | 0.33              |
| 2013-10-02 | 0.00              |
| 2013-10-03 | 0.50              |


