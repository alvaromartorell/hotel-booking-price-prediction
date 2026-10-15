# Hotel Booking Price – Predictive Modeling

This project uses hotel reservation data to predict the **average price per room** of a booking from its characteristics. Several regression models were trained on more than 36,000 real reservations and compared on a held-out test set.

## 📊 Dataset
- Source: Kaggle (Ashan Raza)
- 36,275 hotel reservations, no missing values
- Mixed numerical and categorical variables
- Target: `avg_price_per_room` (average price per night of the booking)

## 🎯 Objective
To estimate the price of a booking from information known when it is made, and to see which characteristics have the largest effect on price.

The exploratory analysis also looks at cancellations (`booking_status`): cancelled bookings tend to have long lead times (more than 100 days) and lower prices.

## 🔢 Features
The models use eight numerical variables, standardised:
- Number of adults and children
- Weekday and weekend nights
- Lead time (days between booking and arrival)
- Number of special requests
- Previous cancellations and previous completed bookings

## 🧠 Models Used
- Linear Regression
- Ridge & Lasso Regression
- K-Nearest Neighbors (KNN)
- Decision Trees
- Random Forest

## 🛠️ Technologies
- Python
- Scikit-learn
- Pandas, NumPy
- Matplotlib, Seaborn

## 📈 Evaluation Metrics
- Root Mean Squared Error (RMSE)
- Mean Squared Error (MSE)
- R² Score

## 📝 Results Summary
Test RMSE with an 80/20 train/test split, as reported in `Reservas_de_hotel.pdf`:

| Model | Test RMSE |
|---|---|
| Linear Regression | 30.79 |
| Ridge / Lasso (small α) | 30.79 |
| Decision Tree (depth 10) | 28.80 |
| KNN (k = 10) | 27.75 |
| Random Forest (100 trees, depth 10) | 27.61 (R² = 0.36) |

- The non-linear models (Random Forest and KNN) give the lowest errors.
- The number of adults and children has the largest effect on price.
- The R² of 0.36 shows that these variables explain only part of the price. Room type, season and booking channel were not used as features and are the natural next step.

## 📂 Files
- `CODIGO HOTEL BOOKING CANCELATIONS.py`: preprocessing, exploratory analysis and models
- `Reservas_de_hotel.pdf`: full report in Spanish, with context, figures and interpretation

The script uses a different random split (`random_state=42`) from the one in the report, so its results may differ slightly from the table above.

## 🔗 Authors
Team project for a Machine Learning course:
- Víctor Suesta – [LinkedIn](https://www.linkedin.com/in/víctor-suesta-arribas-7b1250322/)
- Álvaro Martorell
- Éden Meshulam
