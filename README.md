
SupplyChainIQ
Real-Time Supply-Chain Disruption Predictor. Predict shortages before they happen. Act before sales are lost.

Built by Team Shrey for MineArena 1.0 at University of BDT College of Engineering, Davanagere.

Live demo: https://avi0nash001.github.io/SupplyChain-IQ/

What it does

Late deliveries and sudden demand swings cause stockouts, and most teams find out only after the shortage has happened. SupplyChainIQ watches inventory, order and delivery events as they happen, predicts which items will run out before their delivery arrives, and tells the user what to do about it.

Try it in 30 seconds
Open the live demo, or open index.html in any browser. No install, no server.
Watch the live event stream and the risk ranking update.
Click any item to see why it is at risk, the reorder quantity and the ranked backup suppliers.
Drag the what-if sliders to test a delivery delay or a demand spike.
Press Inject disruption to trigger a new shortage alert.
How the logic works
Days of stock left = current stock ÷ daily usage (usage includes any demand spike)
Margin = days of stock left − delivery ETA (including delays). Below 0 means stockout before delivery.
Risk level: Critical (margin below 0), High (below 2 days), Watch (below 5 days), Safe
Reorder quantity = usage × (lead time + 3-day buffer) − current stock
Backup suppliers: those that arrive before stockout come first, cheapest first
Features

Live event engine, predictive shortage alerts, smart reorder advice, explainable evidence, backup supplier options and a what-if simulator.

Demo vs production

This demo is a single HTML file (HTML, CSS, JavaScript) driven by a built-in event simulator. The planned production architecture:

Event sources (API, CSV, simulator) → Kafka or Redis Streams → Python stream processor → PostgreSQL → forecast and risk engine (Pandas, statsmodels, Prophet) → recommendation engine → FastAPI → Streamlit dashboard with email and SMS alerts.

Login with role-based access, TLS encryption, audit logs and Docker deployment run across all layers.

Roadmap
Foundation: data simulator, SQL schema, stock and usage calculations
Streaming: event stream, delay and shortage detection
Intelligence: forecasting, reorder advice, Streamlit dashboard
Hardening: security, testing, pilot with a real shop

Future scope: supplier APIs, multi-warehouse support, mobile alerts.

Team Shrey

Avinash H V, Kushal S, Rishikesh Koushik, Vinay H M
