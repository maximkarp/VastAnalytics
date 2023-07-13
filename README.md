# Vast Cloud GPU Utilization and Price Analytics
## QUESTIONS
Some questions hosts may have when setting their rental offers for their GPU cloud servers:
* How many minimum GPUs should I set in my offer?
* Is 1 better than 4? 4 take longer to get hired, but lock in utilization. How to decide?
* How do I set my initial price for highest utilization?
* How long should a lower price be offered before lowering it again?
* Is a higher rice at a lower utilization better than a lower price with higher utilization?
## USE CASES
The following use cases begin to address these questions:
* Correlate the metrics driving the hosts with the highest utilization and revenue.
* Focus on metrics related to specific numbers of GPUs for a GPU type, what customers are renting them at, their cycle time to get rented, and how to dial in the best price.
* Live, aggregate historical, and time series utilization min - avg - max pricing and avg duration (gpu name - gpu num).
* How long do machines take to get verified (per machine, gpu name - gpu num)?
* How long does an offer with the price dialed in initially stand before rented (per machine, gpu name - gpu num)?
* Idle time between rentals (per machine, gpu name - gpu num).
* $/DLPerf analysis.
* Duration analysis.
* Correlations between DLPerf, pricing, num GPUs, duration.
* Rentals per second - host - machine - gpu name - num gpus.
* Heatmap for live rental prices (gpu name - gpu num).
* How often does a machine change its offer from listing until rented?
## SOLUTION
We are in progress of developing a Vast.ai data analytics cloud API that does the following:
* Ingests all Vast offers and machine specs every 5 minutes into a time series DB (MySQL). We extract key relational data from the JSON returned by Vast and then store both in indexed tables.
* Perform utilization analysis per sample ingested.
* Expose raw and analyzed data in Grafana.
* Expose raw and analyzed data via REST API.
