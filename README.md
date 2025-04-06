# 🛺 Optimizing Ride-Hailing Services with Data Analytics 🛺

Excited to share my latest project where I analyzed Namma Yatri ride data using SQL and Power BI to extract key insights on ride performance, cancellations, and user behavior!

## 📊 Key Highlights:
✅ Developed an interactive dashboard to track key ride metrics, including trip searches, fare estimates, driver availability, and ride completions.  
✅ Identified high drop-off rates in the booking process—only 45% of searches resulted in completed rides.  
✅ Analyzed driver performance, cancellation trends, and peak demand hours to improve operational efficiency.  
✅ Examined location-based trip trends to identify high-demand areas and optimize driver allocation.  
✅ Evaluated payment trends, revealing that UPI transactions dominate but optimizing payment incentives could drive higher revenue.

## 🔍 Actionable Insights:
📌 Reduce drop-offs by introducing fare discounts or promotions after users view price estimates.  
📌 Prioritize reliable drivers by tracking and rewarding those with low cancellation rates.  
📌 Encourage UPI payments through cashback incentives to boost cashless transactions.  
📌 Optimize driver availability in high-demand locations to improve ride fulfillment.

---

## 📉 Funnel Drop-off Analysis:

### 1. Searches → Got Fare Estimate (81%)  
🟥 **Drop-off: 19%**  
**Reason: Fare estimate fails to load**  
- No route available  
- Backend delay or timeout  
- Unserviceable locations  
- UI bugs, app crashes  

💡 **Suggestion:**  
- Monitor failed estimate logs by `location_id`  
- Add a fallback: “Route not available, retry?”

---

### 2. Fare Estimate → Request Ride (83%)  
🟥 **Drop-off: 17%**  
**Reason: User hesitated to proceed**  
- Fare too high or unexpected  
- Just checking prices (no intent to ride)  
- No offers/discounts  
- Better deals on Ola/Uber  

💡 **Suggestion:**  
- Introduce fare comparison widget: “₹50 cheaper than other platforms”  
- Highlight benefits like “No surge pricing”, “Direct to driver”

---

### 3. Request Ride → Got Driver Quote (88%)  
🟥 **Drop-off: 12%**  
**Reason: No driver accepted the request**  
- Drivers ignoring pings (supply shortage)  
- Odd routes or short-distance rides not profitable  
- Driver app inactive  

💡 **Suggestion:**  
- Incentivize low-demand areas  
- Show users estimated wait time (e.g., “No drivers nearby” vs false hope)  
- Add “Notify me when a driver is available” feature

---

### 4. Got Quote → OTP Entered (77%)  
🟥 **Drop-off: 23%**  
**Reason: Booking canceled before pickup**  
- Customer canceled  
- Driver canceled  
- Long wait time after driver match  
- Mismatch in pickup expectations  

**From data:**  
- Customer Cancellations: 1041  
- Driver Cancellations: 1021  

💡 **Suggestion:**  
- Show “Driver X mins away” and allow pre-cancellation only with reason  
- Penalize repeated cancellations (esp. drivers)  
- Add live status: "Driver en route / OTP screen activated"

---

### 5. OTP Entered → Ride Completed (100%)  
✅ **Perfect retention!**  
If OTP is entered, the trip is always completed — shows strong reliability once the ride starts.

---

## 🛠 Tools Used:
- SQL  
- Power BI
