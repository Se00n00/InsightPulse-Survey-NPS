# InsightPulse-Survey-NPS

<h1>About NPS(Net Promoter Score)</h1>
NPS serves as a widely employed metric across various industries to monitor customer satisfaction levels. The evaluation involves posing the question, "How likely would you recommend this product to a friend or family member?" whereby customers assign a rating on a scale ranging from 0 to 10.

Customers providing ratings between 0 and 6 are categorized as 'detractors.' These individuals discourage others from using the product and are unlikely to make repeat purchases.

Those rating the product with a 7 or 8 are termed 'passives.' While they do not actively endorse the product to their networks, they also refrain from discouraging others.

Customers assigning a rating of 9 or 10 fall into the category of 'promoters.' They actively advocate for the product and are more likely to become repeat customers.

The NPS calculation involves determining the percentage of promoters divided by the total number of customers, subtracted by the percentage of detractors divided by the total number of customers. Although passives are not directly factored into the calculation, their presence influences the percentages. Having more passives is preferable to having more detractors since passives do not count against the percentage of promoters.


<h3>Documentation for Customer Simulation Code</h3>
Overview:
This Python script is designed to simulate customer activities and generate Net Promoter Scores (NPS) over a specified period. The simulation incorporates various factors, including product stability, customer behavior, and the influx of new customers. The primary goal is to analyze how these factors influence NPS trends and overall customer satisfaction.

Files:
Main Script:
File Name: customer_simulation.py
Usage: Execute this script to run the customer simulation.
Supporting Modules:
person.py:

Purpose: Defines the Person class, representing individual customers.
Attributes:
id: Unique identifier for each customer.
created_at: Date when the customer was created.
is_premier: Boolean indicating whether the customer is a premier customer.
is_spam: Boolean indicating whether the customer is flagged as spam.
activity_chance: Probability of the customer being active on a given day.
Methods:
get_nps(stability): Calculates the Net Promoter Score based on stability.
nps_utils.py:

Purpose: Contains utility functions for NPS calculations and randomization.
Functions:
generate_random_nps(weights, num_samples): Generates random NPS scores based on specified weights.
get_adjusted_weights(base_weights, adjustments): Adjusts base weights for NPS distribution.
flip_coin(probability): Simulates a coin flip with the given probability.
get_random_date(start_date, end_date): Generates a random date within a specified range.
calculate_nps(scores): Calculates the Net Promoter Score based on a list of scores.
Global Constants:
DATE_START and DATE_END: Define the start and end dates of the simulation period.
GLOBAL_CUSTOMER_ID: A global variable used to generate unique customer IDs.
Monthly Variations:
Variables:
num_new_customers:

Purpose: Represents the average number of new customers joining per day for each month.
Data: List of integers corresponding to each month.
very_bad, bad, normal, good, very_good:

Purpose: Monthly variations for customer satisfaction scores.
Data: Lists of float values representing adjustments to NPS scores.
stability_weights:

Purpose: Product stability weights for each month affecting NPS distributions.
Data: List of lists containing weight adjustments for each month.
stabilities:

Purpose: Raw stability values for each month, representing product stability.
Data: List of integers indicating product stability levels.
Customer Generation:
Function: get_new_customers(date, n=1000, weight_adjustment=normal, product_stability=0)
Purpose: Generates new customers with random NPS scores.
Parameters:
date: Current date for customer creation.
n: Number of new customers to generate.
weight_adjustment: Adjusts weights for NPS score distribution.
product_stability: Represents the stability of the product.
Main Simulation Loop:
Function: main()
Purpose: Simulates customer activities and generates NPS scores over the specified period.
Components:
Tracks existing and new customer data.
Outputs monthly statistics.
Writes customer and score data to CSV files.
Monthly Variations in Simulation Loop:
The script adjusts customer activities and NPS scores based on monthly variations in stability, customer acquisition rates, and satisfaction levels.
Output Files:
customer.csv:

Purpose: Records customer data.
Columns:
id: Customer ID.
created_at: Date when the customer was created.
is_premier: Boolean indicating premier status.
is_spam: Boolean indicating spam status.
score.csv:

Purpose: Records NPS scores.
Columns:
id: Score ID.
customer_id: Customer ID associated with the score.
created_at: Date when the score was generated.
score: NPS score.
Execution:
Run the script using the command python customer_simulation.py.
The simulation progresses day by day, generating customer activities and NPS scores.
Monthly statistics are printed, and customer and score data are saved to CSV files.
Considerations:
The script uses randomization for customer creation and NPS score generation.
Adjustable parameters include the simulation period, customer behavior, and monthly variations.
Dependencies:
datetime: Used for handling date and time information.
random: Provides functions for random number generation.
Conclusion:
This simulation script serves as a flexible tool for understanding customer dynamics and NPS variations over time. It allows for customization of parameters, making it suitable for different scenarios and analyses. The modular structure facilitates easy extension and modification for specific use cases.

<h2>Demo Link</h2>
https://drive.google.com/file/d/1rTpChsN7cvm_BgGe1CpYyhD5T9zPhN0b/view
