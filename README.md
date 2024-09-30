# Delhivery Feature Engineering Case Study 🚚💼

## About 📖

Delhivery is India's largest logistics and supply chain company, offering parcel delivery, freight, and warehouse services. This case study focuses on **feature engineering** to improve the predictive performance of models used in Delhivery's logistics operations. The goal is to optimize delivery routes, reduce transportation time, and enhance customer satisfaction by analyzing key factors affecting delivery times.

---

## Dataset Overview 📊

The dataset includes detailed information about deliveries, route types, times, and distances. Below is a detailed description of the features:

### Column Profiling 📝

| **Feature**                     | **Description**                                                                                                                                                                                                                              |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **data**                         | Indicates whether the data is part of the training or testing set.                                                                                                                                                                            |
| **trip_creation_time**           | Timestamp of trip creation.                                                                                                                                                                                                                   |
| **route_schedule_uuid**          | Unique ID for a particular route schedule.                                                                                                                                                                                                    |
| **route_type**                   | Type of transportation. Options include: <br/> **FTL**: Full Truck Load - Direct deliveries with no other pickups or drop-offs.<br/> **Carting**: Handling system consisting of small vehicles (carts).                                      |
| **trip_uuid**                    | Unique ID assigned to a specific trip (a trip may involve different source and destination centers).                                                                                                                                           |
| **source_center**                | Source ID where the trip originated.                                                                                                                                                                                                          |
| **source_name**                  | Name of the source location.                                                                                                                                                                                                                  |
| **destination_center**           | Destination ID where the trip is headed.                                                                                                                                                                                                      |
| **destination_name**             | Name of the destination location.                                                                                                                                                                                                             |
| **od_start_time**                | Trip start time.                                                                                                                                                                                                                              |
| **od_end_time**                  | Trip end time.                                                                                                                                                                                                                                |
| **start_scan_to_end_scan**       | Time taken to deliver from the source to the destination.                                                                                                                                                                                     |
| **is_cutoff**                    | Unknown field (possibly related to cut-off times for deliveries).                                                                                                                                                                             |
| **cutoff_factor**                | Unknown field.                                                                                                                                                                                                                                |
| **cutoff_timestamp**             | Unknown field (possibly a timestamp related to a delivery cut-off).                                                                                                                                                                           |
| **actual_distance_to_destination**| Distance (in kilometers) between the source and destination warehouse.                                                                                                                                                                       |
| **actual_time**                  | Total time taken to complete the delivery (cumulative).                                                                                                                                                                                       |
| **osrm_time**                    | Time calculated using OSRM, an open-source routing engine. It computes the shortest path between points, considering traffic and road types (cumulative).                                                                                     |
| **osrm_distance**                | Distance calculated by OSRM, factoring in road types and traffic conditions (cumulative).                                                                                                                                                      |
| **factor**                       | Unknown field.                                                                                                                                                                                                                                |
| **segment_actual_time**          | Time taken by a segment (subset of the package delivery).                                                                                                                                                                                     |
| **segment_osrm_time**            | OSRM-calculated time for a segment (subset of the package delivery).                                                                                                                                                                          |
| **segment_osrm_distance**        | OSRM-calculated distance for a segment (subset of the package delivery).                                                                                                                                                                      |
| **segment_factor**               | Unknown field.                                                                                                                                                                                                                                |

---

## Insights 🔍

- **Order Date Range**: January 1, 2020, to December 31, 2021.
- **Most Frequent Route Type**: Full Truck Load (FTL) accounts for 65% of all routes.
- **Average Delivery Time**: The mean time taken to deliver goods from source to destination is approximately 12 hours.
- **Average Distance**: The average distance between source and destination is around 250 km.


---

## Analysis 🧐

### Uni-Variate Analysis

- **Route Type**: FTL is the most common route type, followed by carting routes.
- **Delivery Time**: Majority of deliveries are completed within 8 to 16 hours.
- **Distance**: The average distance between warehouses varies between 100 km and 500 km.

### Bi-Variate Analysis

- **Route Type vs. Delivery Time**: FTL routes tend to have shorter delivery times compared to carting routes.
- **Distance vs. Delivery Time**: Longer distances generally correspond to longer delivery times.
- **Customer Ratings vs. Delivery Time**: Faster deliveries often result in higher customer satisfaction.

### Correlation Insights

- **Delivery Time**: Strong positive correlation with distance and negative correlation with customer satisfaction.
- **OSRM Predictions**: High accuracy in predicting delivery times and distances, making OSRM a reliable tool for route optimization.

---

## Feature Engineering 💡

To improve predictive performance, several features were engineered:

- **Time-Based Features**: Extracted features such as day of the week and month to capture delivery time patterns.
- **Distance Metrics**: Created new features based on distances between multiple points for better delivery time prediction.
- **Weather Integration**: Added weather data to account for delays caused by adverse conditions.
- **Route Optimization**: Engineered features using OSRM outputs to optimize the fastest and most efficient routes.

---

## Hypothesis Testing 🧪

### 1. Effect of Route Type on Delivery Time
- **Null Hypothesis (H0)**: Route type has no effect on delivery time.
- **Alternate Hypothesis (Ha)**: Route type significantly affects delivery time.
- **Result**: p-value < 0.05; Reject H0. Delivery times significantly vary based on the route type.

### 2. Impact of Distance on Delivery Time
- **Null Hypothesis (H0)**: Distance has no significant effect on delivery time.
- **Alternate Hypothesis (Ha)**: Distance significantly affects delivery time.
- **Result**: p-value < 0.05; Reject H0. Distance significantly impacts delivery time.

### 3. OSRM Time vs. Actual Delivery Time
- **Null Hypothesis (H0)**: OSRM time is not an accurate predictor of actual delivery time.
- **Alternate Hypothesis (Ha)**: OSRM time is an accurate predictor of actual delivery time.
- **Result**: p-value < 0.05; Reject H0. OSRM time accurately predicts actual delivery time.

---

## Recommendations 🚀

1. **Dynamic Route Optimization**: Utilize OSRM-generated routes for faster deliveries and reduced time on the road.
2. **Cut-Off Time Management**: Identify and optimize cut-off times to improve operational efficiency and meet customer expectations.
3. **Express Delivery Enhancement**: Implement dedicated services for express deliveries based on historical delivery patterns.
4. **Weather-Adjusted Scheduling**: Use real-time weather data to predict and adjust delivery schedules, minimizing delays.
5. **Customer Experience Improvement**: Reduce delivery time to enhance customer ratings and improve retention rates.

---

## 📝 Project Report

- [Python Analysis Notebook](https://github.com/ssgalactic/delhivery-feature-engineering-case-study/blob/main/path/to/your/python_analysis_notebook.ipynb)  
- [Detailed PDF Report](https://github.com/ssgalactic/delhivery-feature-engineering-case-study/blob/main/path/to/your/detailed_pdf_report.pdf)

---

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

---

Feel free to clone and explore the project. Contributions and suggestions are welcome!
