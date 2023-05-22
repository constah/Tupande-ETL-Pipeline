# Tupande-ETL-Pipeline
You have been given four datasets in CSV format containing the following fields:

1. contract_offers: Contains information about the contract offers made to customers for different loan products. The fields include:
● offer_id: Unique identifier for the contract offer.
● offer_name: Name of the contract offer.
● offer_type: Type of the contract offer (e.g., group, individual, cash).

2. contract_payments: Contains information about payments made by clients towards a contract.
● Id: Unique identifier for the payment
● Contract_reference: Unique contract identifier
● type: Type of payment
● amount_paid: Amount paid by the client

3. contracts: Contains information about the current status of contracts for different loan products. The fields include:
● reference:Unique identifier for the contract.
● status: Current status of the contract (e.g., active, completed).
● start_date: The day the contract started
● offer_id: The unique identifier for the contract offer
● Lead_id: Unique identifier for the lead

4. leads: Contains additional information about the client and contract
● id: Unique identifier for the lead.
● contract_reference: Unique identifier for the contract
● State: The state the client comes from
 ● County: The county the client comes from

Your task is to design and implement a data pipeline to process these datasets and generate a dataset for the Tupande field team.
Tasks:
1. Write a python script that performs ETL, moving the csv files from your PC to a database(You are free to use any locally/cloud hosted database or datawarehouse platforms)
2. Use SQL or Python to generate the derived columns below
3. Produce a final dataset(containing the derived columns) as a table in the database/data
warehouse.
4. Submit an executable python script that combines both processes.
The Columns to be generated are:
1. End date: The end date of the loan, calculated as start_date + 180 days.
2. Loan type: The type of the loan product, derived as follows:
● If offer_name contains 'group', the loan type is 'Group loan'.
● If offer_name contains 'individual', the loan type is 'Individual loan'.
● If offer_name contains 'cash', the loan type is 'Cash sale'.
3. Maturity date: The maturity date of the loan, calculated as end_date + 30 days if loan_type is 'Group loan', 30 days if loan_type is 'Paygo loan', and 60 days if loan_type is 'Individual loan'.
4. Quarter due in: The quarter in which the loan is due, derived from the maturity date.

Final dataset should contain the below columns:
● Contract_reference ● Status
● loan_type
● Start_date
● End_date
● Maturity_date
● nominal_contract_value ● Cumulative_amount_paid ● State
● county

You are free to use any tools or technologies you are comfortable with, but you should justify your choices in terms of their suitability for the task. You should also consider scalability, fault tolerance, and cost efficiency when designing the pipeline.
Deliverables:
1. Design document: A document outlining your proposed data pipeline design, including a justification for the tools and technologies you have chosen.
2. Code: you are required to submit code files used to implement the pipeline
3. Results: You are required to submit a sample of the dataset produced by your pipeline. This can be a simple csv file.
