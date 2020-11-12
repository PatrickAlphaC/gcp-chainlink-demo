# gcp-chainlink-demo

We are going to be going through 3 things in this repo.

1. Setup a node on the GCP
2. Setup a bigquery external adapter
3. Connect bigquery external adapter to Cloud Funciton
4. Run end-to-end demo

Then, with all these steps, you should be able to: 
1. Use this data in your smart contracts! 

# Quickstart

1. Create a [free GCP account](https://console.cloud.google.com/)
You'll have to add a credit card, but don't worry! You won't be charged unless you turn on automatic payments. You get a free trial of $300 for up to a year. 

You'll have to enable a few APIs including:
[BigQuery](https://console.cloud.google.com/flows/enableapi?apiid=bigquery&_ga=2.104006281.802978260.1605093328-241701440.1605093193)

2. Setup a Chainlink VM
Ubuntu
1 or 2 cores
10 GB SSD is fine

3. Setup PSQL DB (will take a minute)

enable networking API (search bar)
Add access context manager, compute OS Admin login, compute viewer to your users roles. (in IAM & Admin)

Add a user
Add a database

4. [Install the google cloud SDK](https://cloud.google.com/sdk)

5. ssh tunnel into the VM

Replace `project_id`, `zone` and `vm_name` respecfully
`gcloud compute --project "project_id" ssh --zone "zone" "vm_name" -- -L 6688:localhost:6688`

6. Follow the [Running a Chainlink node](https://docs.chain.link/docs/running-a-chainlink-node) docs to setup a UI

You'll want to use an ETH client for your ETH_URL. We'll use [Fiews](https://dashboard.fiews.io/home#)

7. Follow the [Fulfil Requests](https://docs.chain.link/docs/fulfilling-requests) to fulfil your first request

8. Setup your [Google Cloud External Adapter](https://github.com/PatrickAlphaC/bigquery-cl-ea)

Let's go to the [bigquery UI](https://console.cloud.google.com/) and run some sample SQL commands

Deploy your EA to Cloud funcitons (instructions in the readme of the bigquery EA repo)

Add your bridge to your node, then add that jobId to your get request in your solidity contract. 

You can also check out the [BigQuery command line](https://cloud.google.com/bigquery/docs/quickstarts/quickstart-command-line) 



