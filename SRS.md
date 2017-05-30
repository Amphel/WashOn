# Software Requirements Specification

##### for
# WashOn

### Version 1.0 

#### Prepared by
##### A. Ampilogov
##### O.Semenova

##### 24.05.2017





# Table of Contents

1. [Introduction](#Introduction)  
1.1 [Document conventions] (#Document_conventions)  
1.2 [Intended audience and Reading Suggestions] (#audience)  
1.3 [Project Scope] (#ProjectScope)  
1.4 [References] (#References)  
1.5 [Definitions, Acronyms, and Abbreviations] (#Definitions)  
   
2. [Overall Description] (#OverallDescription)  
2.1 [Product perspective] (#ProductPerspective)  
2.3. [Product features] (#ProductFeatures)  
2.3 [User classes and characteristics] (#UserClasses)  
2.4 [Operating environment] (#OperatingEnvironment)  
2.5 [User environment] (#User environment)  
2.6 [Design/implementation constraints] (#constraints)  

3. [External Interface Requirements] (#InterfaceRequirements)  
3.1 [User interfaces] (#UserInterfaces)  
3.2 [Hardware interfaces] (#HardwareInterfaces)  
3.3 [Software interfaces] (#SoftwareInterfaces)  
3.4 [Communication protocols and interfaces] (#CommunicationProtocols)  
 
4. [System Features] (#SystemFeatures)  
4.1 [System feature “Placing orders without registration”] (#OrdersWithoutRegistration)  
4.2	[System feature “Online payment”] (#OnlinePayment)  
4.3	[System feature “Address search”] (#AddressSearch)  
4.4	[System feature “Amazon Web Services”] (#AWS)  

5. [Other Nonfunctional Requirements] (#OtherRequirements)
5.1 [Performance requirements] (#PerformanceRequirements)
5.2 [Security requirements] (#SecurityRequirements)
5.3 [Software quality attributes] (#SoftwareQualityAttributes)




# 1. <a name="Introduction"></a> Introduction

1.1	Document conventions
This document follows MLA Format (Modern Language Association). Bold-faced text has been used to emphasize section and sub-section headings. Highlighting is to point out words in the glossary and italicized text is used to label and recognize diagrams.

1.2	Intended audience and Reading Suggestions
This document is to be read by the development team, the project managers, testers and documentation writers. The SRS has been organized approximately in order of increasing specificity. The developers and project managers need to become intimately familiar with the SRS.

1.3	Project Scope
WashOn is software providing its customers in Chile with the ability to have their clothes, linen and home items to be washed, ironed, well folded and specially cleaned. The service includes pick up and drop off of the items by a driver. Customers’ household laundry is picked up at their premises and delivered back minimum in two days.
Those who wish to use the service do not need register in. Therefore, this makes the application simple to use. However, personal accounts are available on the site, where customers can find the history of their orders.
The availability of the service is restricted through the geographical areas.
 
1.4	Definitions, Acronyms, and Abbreviations

Configuration	It means a product which is available / Selected from a catalogue can be customized.

---
Expressions: Serverless V1.0 Beta 2
Description: "Source control	
AWS	
	
	
Pick up	
Drop off	
Dispatch	
Delivery	
Laundry	partner
Marketplace	
Actual items/weight	
Journey	pick-up transfer
Journey sheet	
pick-up transfer	
Drop-off transfer	
OrderStatus
	 UnconfirmedByCustomer  = 0,

    WaitingPickup = 10,
    PickupInProcess = 11,
    Pickedup = 12,
    PickupFailed = 13,

    PriceRequested = 20,

    WaitingDropoff = 30,
    DropoffInProcess = 31,
    Dropoffed = 32,
    DropoffFailed = 33,

    Cancelled = 500
driver priority	
super user	
QA	
UAT	"

---






1.5	References
Diagram of status changing from laundry administration’s angle
Flowchart of order flow

2.	Overall Description

This section states product features from customer’s perspective and shows its advantages in comparison to competitors in the market.

2.1	Product perspective
WashOn is an online marketplace enabling people to choose a laundry that will provide the service which includes cleaning, transfer of items and customer support.
The service is provided through the internet website. This allows stakeholders and partners to target wide audience. Customers may use mobile, tablet, laptop or computer devices to acquire the service via a web browser.

2.2	Service context
There are four main contexts 
1)	Customer – service from customer’s angle including placing an order, payment, order tracking and requesting help.
2)	Laundry administration – service from laundry staff perspective including tracking of orders, payments and their drivers.
3)	Driver – service from driver’s point of view including pick up, drop off and order status tracking
4)	WashOn administration – service from administrator’s angle including resolving issues related to the website, maintaining cooperation between customers and laundries, marketing.

2.3	Product features
WashOn will provide a number of functions; each is listed below

2.3.1	Customer
•	Order placing
o	The customer may choose service options (washing, ironing, special cleaning, dry cleaning), fill up order form and submit the order
o	The customer should confirm the order via e-mail.
•	Order cancelation
o	The customer can cancel the order before a driver starts his pick-up transfer.
•	Registration
o	Customer may register in the system via email or social networks
o	After registration the history of orders is available
•	Payment
o	Payment is provided by the third-party service called Flow.
o	Customer can pay online by credit card or OneClick service.
•	Order tracking
o	The customer should receive an email in case of any change of the order
•	Requesting help
o	The contact information must be provided to the customer.
	Laundry contacts
	WashOn contacts	
•	Localization
o	The customer part of the website is available in Spanish and English. Spanish is the primary language.

2.3.2	Laundry administration
•	Order tracking
o	Laundry staff may subscribe to changes of orders
•	Order status changing
o	Laundry staff may change order status to 
o	“Cancelled”
o	“Pickedup"
o	“PickupFailed"
o	“Dropoffed "
o	“DropoffFailed”
•	Payment status tracking
o	Laundry staff may subscribe to payment status change
•	Customer support
o	Laundry staff may have the access to customers’ contacts
•	Items checking and order correction with actual items and weight
o	Laundry staff may change an order details. Items and weight entered by laundry staff is considered as actual. These data will be used for automatic price calculation. In case laundry staff has not set actual data, the customer’s input will be used for price calculation.
•	Automatic and manual driver appointment
o	As soon as the order is paid by customer, a driver should be automatically assigned to transfer process according to the area and driver priority. Laundry staff may manually assign the order to a driver.
•	List of orders
o	Laundry staff may see the nearest orders that will be being processed by drivers. 
o	Laundry staff may filter orders and see their details.

2.3.3	Driver
•	Order status changing
o	A driver may change the status of an order to 
	“Pickedup",
	“PickupFailed"
	“Dropoffed "
	“DropoffFailed”

o	A driver may add a comment to an order
•	Journey sheet
o	The journey sheet does not contain cancelled and non-confirmed  orders

2.3.4	WashOn administration
•	List of orders
o	WashOn administration may see the nearest orders that will be being processed by drivers. 
o	WashOn administration may filter orders and see their details. 

•	Order correction 
o	As a super user WashOn administration can freely modify any order


2.4	User classes and characteristics
Customer. The person that connects to the on-line e-commerce front-end and browses the product catalog or places an order.
Laundry administrator. The person that looks after the orders and ensures that all the operations work correctly.
Driver. The person who is the part of laundry staff and conveys orders to customers
WashOn administrator. The person that looks after the software and resolve issues related to the work of this software.

2.5	Operating environment 
The website supports 2 last major versions of popular browsers:
o	Intenet Explorer
o	Mozilla Firefox
o	Chrome
o	Opera
o	Safari
Mobile and desktop versions are available for users.
2.6	User environment
This system is a website allowing users to operate over the Internet.

2.7	Design/implementation constraints
The main HTML pages are static content that dynamically loads other parts via JavaScript.
There is no way to prerender full HTML page for devices with disabled JavaScript.

3.	External Interface Requirements

3.1	User interfaces
The next common fields are found across different pages of the application:
Field type	Description
Name	range 1 - 256 UTF-8 characters
Email address	Maximum length is 1024 characters. Follows LDH rule (letters, digits, hyphen), is validated via email confirmation
Address	range 1 - 1024 UTF-8 characters
Description	range 10 – 1024 UTF-8 characters.
Whatsapp	range 5 – 120 UTF-8 characters
Washing weight	range 1 – 150 kg, step is 0.01
Wash Item Count	range 1 – 300, step is 1.0
Password	
Date	Spanish and English format is DD.MM.YYYY
Time	24-hour format

3.1.1	Placing an order
1)	Customer shall fill up the address field (Address type) => available laundries will be shown.
2)	Customer shall choose a laundry => available services and prices will be shown
3)	Customer shall choose at least one service and its options.
4)	Customer shall fill up the form with next fields:
o	Name (Name type)
o	Email (Email address type)
o	Whatsapp (Whatsapp type, optional)
o	Dispatch (Date type and Time type)
o	Delivery (Date type and Time type)
o	Comment  (Description type)
5)	Customer shall agree with terms and conditions of use
6)	Customer shall submit the entered data.

3.1.2	Registration

3.2	Hardware interfaces

3.3	Software interfaces
1.	The WashOn system shall interact with “Flow” system which provides payment integration. Every interaction should be logged.
2.	The WashOn system shall interact with “Mailgun” service which sends emails and notifies about message delivery status.

3.4	Communication protocols and interfaces
The system shall use the HTTP protocol for communication over the internet in development, QA, UAT stages, while HTTPS shall be used for production.

4.	System Features

4.1	System feature “Placing orders without registration”
A customer may place orders without any registration.

4.2	System feature “Online payment”
A customer may pay online with credit card on one click.

4.3	System feature “Address search”
Automatic google address search makes the software for customers easy to use.

4.4	System feature “Amazon Web Services”
AWS provides reliable and fast hosting.


5.	Other Nonfunctional Requirements

5.1	Performance requirements
The website shall support 50 requests per second in production
95% of the transactions shall be processed in less than 5 second
90% of emails shall be received in 5 minutes, the rest are in 15 minutes

5.2	Security requirements 
Separate login shall be used for development, QA, UAT with the following rights:
Invoking AWS functions
Deploying software
Database and S3 storage access
Separate login shall be used for production and only accessible to stakeholders and main developer.

5.3	 Software quality attributes
Software shall have unit tests, functional testing, end-to-end system testing.

