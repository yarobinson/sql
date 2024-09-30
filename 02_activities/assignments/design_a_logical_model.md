# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).

![image - Question 1] sql/02_activities/homework/images/SQL Assignment - Question1.drawio.png

## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.

![Image - Question 2] sql/02_activities/homework/images/SQL Assignment - Question 2.drawio.png

## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._

Bonus: Are there privacy implications to this, why or why not?
```
Your answer...
```
A type 1 architecture would allow for existing values in the customer_address table to be overwritten by new values and overwritten values would not be retained. For example - when a customer changes their address, the update overwrites the existing customer information. A useful column to have in this table would be last_updated to track when a customer's information is updated. 


A type 2 architecture would allow for existing values and new values to exist within the same table. For example - when a customer changes their address, a new entry would be created in the table corresponding with the existing customer_id alongside the new address information. Following this change, there would be two entries with the same customer_id but different address information. The last_updated column would be useful in this structure as well to track the new and old values. 

Bonus question: With retaining any customer information, there is always the question of security. Customer information should be stored while considering data storage, data handling, etc. A type 1 structure would a safer option than type 2 due to not retaining obsolete customer information. 

With a type 2 structure, there would need to be guidelines on how long to store obsolete customer information, how to handle customers who would like data deleted and data storage for relevant information + obsolete information. 

## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
Your answer...
```
Two differences between my ERD and the AdventureWorks ERD are; 
1 - The AdventureWorks ERD has tables organized into various schemas depending on the part of the business that the data belongs to. For example, the product related tables are in the production schema. 
2 - The AdventureWorks ERD identifies whether a value is a primary key or foreign key. 
3 - There is a much more detailed breakdown of the sales information compared to my ERD. The sales schema goes beyond customer and purchases tables to include credit card information and currency information. 

If I could change anything in my ERD, I would have followed the AdventureWorks template and organized my tables into schemas. I think this change could have organized by ERD a bit better. 

# Criteria

[Assignment Rubric](./assignment_rubric.md)

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `September 28, 2024`
* The branch name for your repo should be: `model-design`
* What to submit for this assignment:
    * This markdown (design_a_logical_model.md) should be populated.
    * Two Entity-Relationship Diagrams (preferably in a pdf, jpeg, png format).
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sql/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `model-design`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-4-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
