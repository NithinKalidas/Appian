# Intro and Projects

Hi, I’m Nithin Kalidas, an Appian Certified Associate Developer with over 3.5 years of experience working at Tata Consultancy Services. I’ve been primarily involved in enterprise banking and retail loan processing applications, where I design and deliver end-to-end BPM solutions using Appian. I have strong hands-on experience with SAIL interfaces, Process Models, Records, CDTs especially with core banking systems like T24.

Roles and Responsibilities:
My roles and responsibilities to work on assigned (align with) user story, development performing unit testing and so on. 

Current Work Item,
Working on user story related to send back cases from operation maker to operation checker

RLP: 

1. Request Details -> Campaign, Channel, Branch or Mobile Application 
Application Products: 
Credit Card, ICC (Islamic Credit Card), Personal Loan, Personal Finance, Personal Loan + Credit Card, Auto Loan, Auto Finance, Housing Loan, Housing Finance, Over Draft, 
Personal Loan (against Salary) + Credit Card, Over Draft (against FD)

2. Application Check 
Get Applicant, Co-Applicant, Guaranter
check for New To Bank (NTB) or Existing to Bank (ETB)
Check for PEP (Politically Exposed Person), Perform World Check with RPA

3. Application Details:
Personal Details -> Name, Age, Gender, Citizenship 
Identity -> Emirates Id
Family
Address Details
Occupational Details
Income Details
Expense Details

4. Applicant Details: 
Liabilities Check (NBF Loan and Other Bank Loans)
if Nbf Loan, those Details are fetched Using integration
Policy will be fetched for loan details -> Loan Amount, Tenuse, Interest rate
Loan Type, Max tenure, Max cap, Max income multiplies

5. Loan Amount (send/Receive)
NTB -> Either New Account or Existing Bank Account
ETB ->  Existing Account

Oracle Revenue Management & Billing (ORMB) Fee -> For Processing Fee Calculation 

6. Assets & Collateral:
Search for NBF Only
If FD exist -> FD Call will list all the FD's and they can take 90% of FD

Mortage -> AL (check for new or used vehicle), HL
Take Insurance -> Loan Insurance/Personal Insurance (small amount of Fee)
Bank Statemet checks
Application Duplicate Check with CIF, Firstname, Passport, Mobile, Account number, Application reference number

Deviation: 
Recommended Interest rate, 
Loan Amount with max cap, 
Interest rate, 
Tenure
Collateral

7. Sumary View
Interest rate, Salary, Supporting documents, EID
At this time RPA will complete world check



Approval Flow For RLP:
1. Branch Maker/Seller:
2. Branch Checker: Verifies:
3. Retail Credit Investigation Team (RCIT) : under writter, manager, Head Of Sales(HOS)
4. Document Verification (DO):
5. Operation Maker: System Process
6. Operation Checker : T24 Call back,  T24 Validations , CIF Creation/Acc Creation
Operation Checker Can send back to operation maker and with pre populated data and validate the inputs

Letter of Generation: System will generate a PDF with all the details (using Docx)

----------------------------------------------------------------------------------------------

AICB Integration: 
1. System Recommendation -> Debt Burden Ratio (DBR)
2. Under Writter (1st Approval)

API -> Emirates Id -> Report Generate using HTML and converted to PDF
Customer will see a Process Status which runs the process model in ASync and fetched and called everytime clicked on refresh button 

-----------------------------------------------------------------------------------------------

Statement Of Account (SOA)
Satatement Services using NBF Account or CIF number for each product (HL, AL, etc)

Limitation of HTML Doc Creation: 
Modern CSS can be used

Record Action -> Initiate Req -> CIF/Account No -> Statement of Acc -> Export DSE to excel


 
             
              




