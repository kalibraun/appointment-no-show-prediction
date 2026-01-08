# Appointment No Show Prediction
Missed medical appointments reduce care quality and cost healthcare systems millions annually.
This project builds a machine learning model to predict appointment no-show risk so clinics can proactively intervene (e.g., reminders, overbooking, or rescheduling).

---
# Problem Overview 

Missed medical appointments (“no-shows”) are a persistent challenge for healthcare systems. When patients do not attend scheduled appointments, providers lose valuable clinical time, operational costs increase, and patient care is delayed.

This project builds an end-to-end machine learning model to predict the likelihood that a patient will miss a scheduled medical appointment. The goal is to support proactive intervention strategies, such as targeted reminders or scheduling adjustments, to reduce no-show rates and improve healthcare delivery efficiency.

# Business Objective 
Healthcare clinics operate with limited staff time and resources. Blanket interventions (e.g., sending reminders to all patients) can be inefficient and costly.

Objective:

Develop a predictive model that assigns a no-show risk score to upcoming appointments so clinics can prioritize interventions for the highest-risk cases.

Example decisions enabled by this model:
* Targeted SMS or phone call reminders
* Selective overbooking strategies
* Rescheduling high-risk appointments to lower-impact time slots

# Machine Learning Problem Definition

Task: Binary classification

Target Variable: no_show (1 = patient did not attend, 0 = attended)

Prediction Timing: Before the appointment occurs

Output: Probability-based risk score (0–1), not just a class label

Key Challenges: 
* Class imbalance (no-shows are less frequent than attended visits)
* Preventing data leakage from post-appointment information
* Balancing recall and precision to support real-world operational decisions

# Dataset Description
This project uses publicly available medical appointment scheduling data from a large public healthcare system. The dataset includes:
* Patient demographics
* Appointment scheduling details
* Engagement indicators (e.g., SMS reminders)
* Appointment attendance outcomes
