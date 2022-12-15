# Sales-Drivers--IBM-Data-Challenge

		
## Challenge: 		You have been hired as a Data Scientist and Analytics Consultant by the Head of Sales for the hypothetical company SWHub, based in North America.
		You are given a set of data that includes historical North American deals on SWHub products, both won and lost,  from 2019 to 2022. You are also given competitor information on Worldwide deals. Given the products SWHub sells and its competitive landscape, SWHub wants you  to analyze the company's current revenue, winrate and competitor strategy. 
		Every sales deal is uniquely identified by a web quote number. Competitor information for these deals are provided in the form of comments. Please refer to the data dictionary for details on the provided data.
		
		First, identifiy:
		1.1 Across all sales deals, which product type contributes the biggest revenue in 2021? Assume that for any deal, revenue is generated for the year when the deal is submitted.
		1.2 Investigate the most significant drivers for a deal’s  win or loss. While a correlation analysis is a good starting point, ML modeling with new features based on the provided dataset, is strongly recommended.
		1.3 What measures can you take to improve your model(s)’ performance in 1.2 above? 
		1.4 What additional data do you think may be appropriate to enhance your model and why?
		
		Next, combine the historicak deals data with the competitor data, to figure out:
		2.1. Which product type has more competitors on an average? Explain why, both from data and business perspectives, clearly stating your assumptions.
		2.2  How does competitor affect win/loss status of a deal?
		

		
## Additional notes:		Details on product category are listed below:
		SnS Renew = Subscription and Support Renewal, provides both product upgrades and technical support
		SaaS = Software-as-a-Service
		SSW = Standard Software
		Subscription = Subscription is a term license for certain SWHub products, where the client commits to a subscription term. Clients can choose to not renew, but cannot cancel during a term.
		
## Table1 - SW deals
Field Name	DataType	Description
WEB_QUOTE_NUM	Varchar	A sale order deal's unique ID
PROD_CATEGORY	Varchar	Product category categorizes each product ID into SSW, SaaS, SnS Renew, Subscription
CUSTOMER_NUM	Varchar	Unique identifier of the customer/client to whom the product is sold
WON	Integer	Flag indicating the win/loss status of a deal. Deal is considered won when WON=1, otherwise it's a lost deal.
CNTRY_CODE	Varchar	Country code
PART_NUM	Varchar	Product ID of a line item in a given deal; Duplicated product ID can exist in the same deal
PART_QTY	Integer	Product quantity; Quantity can be a huge mumber (i.e, 999999999) and is typically indicative of unlimited licenses.
QUOTE_PRICE	Float	The final total price (in USD) , at part_num level for the given product quantity and license term, at deal close,; Usually it's a discounted price based on entitled_price
ENTITLED_PRICE	Float	Original listed price (in USD) at part_num level
SUBMIT_DATE	DateTime	The date and time when the deal was submitted
EXCHANGE_RATE	Float	Exchange rate of local currency to US dollars at the time when the deal was submiited
CURRNCY_CODE	Varchar	Currency code
START_DATE	DateTime	Start date of the product (the specific software license or service) listed on the deal
END_DATE	DateTime	End date of the product (the specific software license or service) listed on the deal
INDUSTRY_CODE	Varchar	Industry code  that client is categorized in
INDUSTRY_DESC	Varchar	Industry that client is categorized in
SUBMIT_YR	Integer	Year of the submit_date 
		
		
		
## Table2 -  SW deals comments		
" - SW deals' comments with competitor information added/ modified between 1Q2019 to 2Q2022
 - ~ 75K  rows 
 - Data is Worldwide: all deals with competitor information is included
 - Competitor information can be added/modified before or after a deal closed"		
Field Name	DataType	Description
WEB_QUOTE_NUM	Varchar	A deal's unique ID; Primary Key
CMMT_TYPE	Varchar	Comment type. When the value of this field is 'COMP_NAME', the COMMENT field gives the competitor name(s) for the given deal.
COMMENT	Varchar	The content of the comments.
ADD_DATE	DateTime	Date and time when the comment was added 
MOD_DATE	DateTime	Date and time when the comment was modified <img width="815" alt="image" src="https://user-images.githubusercontent.com/42665120/207758650-44b907ac-b1ec-4c0c-b528-75bc954bf189.png">
