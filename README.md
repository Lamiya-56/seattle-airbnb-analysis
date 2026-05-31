# Seattle Airbnb Analysis - Notes

## Methodology

### 1. Data Cleaning
- listings.csv: removed $ and , from price column, converted to float
- calendar.csv: converted date to datetime
- available column: fixed astype(bool) bug using map({'t': True, 'f': False})

### 2. Occupancy Rate
- Per listing: booked days / total days
- available = False means booked

### 3. Merge
- Occupancy rates merged to listings on listing_id / id

### 4. Aggregation
- Median price, avg occupancy, listing count by neighbourhood
- Median used instead of mean (robust to outliers)

### 5. Revenue Potential
- revenue_potential = occupancy_rate x price x 365

---

## 5 Host / Investor Insights

1. Location is everything — 3x price gap between best and worst neighbourhoods
2. Entire home earns 2x more than private room
3. Raise prices in summer (Jun-Aug) by 15-20%
4. Enable instant bookable — no downside, better guest experience
5. Focus on revenue potential (price x occupancy), not just price alone

---

Dataset: Seattle Airbnb Open Data (Kaggle)

Period: January 2016 - January 2017

Listings: 3,818 | Calendar rows: 1,393,570
