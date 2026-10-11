
MapleFreight Delivery Delay Prediction

1. Problem

MapleFreight Logistics is experiencing delivery delays that can lead to customer complaints, service credits, and additional costs. The goal of this project is to analyze shipment data, predict potential late deliveries, and send automated Slack alerts to help the dispatch team take action earlier.

2. Dataset

The dataset contains 6,035 shipment records and 23 columns with information about:

Shipment routes, origin, destination, and distance.
Carriers and service levels.
Shipment weight and number of stops.
Pickup delays, driver experience, and vehicle age.
Weather, traffic, and route congestion.
The target variable, delivered_late (0 = on time, 1 = late).

Approximately 21% of shipments were late, making this an imbalanced classification problem.

3. How to Run
   Download or clone this repository.
   Make sure the notebook and dataset are in the same folder:
   MapleFreight_Delivery_Delay_Prediction.ipynb
   maplefreight_delivery_delay_dataset.csv

Install the required Python libraries:

pip install pandas numpy matplotlib seaborn scikit-learn shap requests python-dotenv
Open the notebook in Jupyter Notebook or VS Code.
Run the notebook cells in order.

Slack integration: To test Slack alerts, configure a Slack Incoming Webhook and store its URL securely in a local environment file. Never upload webhook URLs or other secrets to GitHub.

4. Key Findings
   Longer routes had a higher late-delivery rate: approximately 14% for short routes, 18.7% for medium routes, and 29% for long routes.
   Shipments with adverse weather and high traffic had a late-delivery rate of approximately 39%, compared with 18% for shipments with clear weather and low traffic.
   SHAP analysis identified carrier, number of stops, shipment distance, pickup delay, traffic index, and route congestion as influential model features.
   Logistic Regression achieved 72.3% accuracy, but its recall for late deliveries was only 11%.
   Random Forest achieved 79.7% accuracy, but its recall for late deliveries was only 3%.

These results show that accuracy alone is not enough to select a model. Both models need further improvement in detecting late deliveries.

The Slack integration successfully sent test alerts and was extended to 146 priority shipments with predicted delay probabilities of at least 42%. The integration is a prototype using test data, not a live production monitoring system.

5. AI Usage

ChatGPT was used as an assistant during project development to support Python troubleshooting, explain SHAP and guide in how to write the code, and help organize project documentation.

The Slack integration were performed and tested in the project notebook. AI-generated suggestions were reviewed and adapted to the project.

AI assistance supported the development process.
