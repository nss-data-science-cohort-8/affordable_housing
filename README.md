# Assessing the Impact of Affordable Housing Development

In the last decade, Davidson County has experienced tremendous population growth. With this population growth has come skyrocketing housing costs. From 2010 to 2019, both home values and rents have grown by more than 150%, while wages increased only slowly. High housing costs can squeeze household budgets, reducing the money available for other daily needs, including food, clothing, health care, utilities, and transportation, as well as money needed for education or for future savings.

One method of addressing rising housing costs is by building affordable housing developments. Despite the potential benefits, property owners who live near proposed housing developments often oppose such projects, citing fear that the developments will cause their property values to decline or will increase crime rates.

In this project, you'll be examining the impact of housing units built in Davidson under the the Low Income Housing Tax Credit (LIHTC) or which were funded by the [Barnes Housing Trust Fund](https://www.nashville.gov/departments/mayor/housing/barnes-fund). Established in 1986, the LIHTC program has become an integral component of federal housing policy, funding 21 percent of all multifamily developments over the period 1987-2008. The Barnes Fund, created in 2013, is Metro Nashville's first housing trust fund and was created to leverage affordable housing developments throughout Davidson County.


**About the Data**
The following datasets have been provided for your analysis (download them [here](https://drive.google.com/drive/folders/1zWaLMIVQQuZXp4HHvtdeGpOZ5QYeWGPT?usp=share_link)):

1. filtered_sales.csv:
	* Contains sales of single family homes from 1995 to October of 2022. 
	* Non arms-length transactions and transactions for parcels which did not have a house on them at the time of sale. This was done by removing any transations for $0, any transactions for which the adjacent appraisal values showed $0 for improvents, and any for which the transaction amount was less than half of the adjacent appraisals. 
	* Optional: If you would like to work with the full dataset, all transactions are contained in full_sales.csv and the assessment values are in assessment.csv.
2. LIHTC.csv
	* Details of affordable housing developments funded by the LIHTC program.
	* Refer to the included data dictionary for variable descriptions.
3. barnes.csv
	* Contains information on rental properties that are completed and have more than 10 units which were funded by the Barnes Fund.
4. property_details.csv
	* Contains detailed information on each property, including year built, square footage, number of rooms, and location (lat/lng).

For this project, you'll mimic the methodology of the working paper ["Does Federally Subsidized Rental Housing Depress Neighborhood Property Values?"](https://furmancenter.org/research/publication/does-federally-subsidized-rental-housing-depress-neighborhood-property), building a statistical model to explore the effect on sales price of a home nearby to an affordable housing development and using a difference in differences approach.

**Basic Goals:**

Look at the Park at Richards Road Apartments, which are contained in LIHTC.csv and have a HUD ID of TNA20130015. These were allocated in 2012 and placed in service in 2013.

Find all homes that are less than 2000 feet from this development (our "treatment" group) and all homes that are between 2000 and 3000 feet from this development (our "control" group). For these homes, find all sales that took place between 5 and 1 year before this development was allocated and all sales for 1 to 5 years after it was placed in service. You can use these are the "pre" and "post" sales.

Use a difference in differences approach to estimate whether this development had an impact on sales prices. Start with a basic model for the sales amount based on the pre/post and treatment/control variables only. Can we conclude that the sales price for nearby homes was affected by the development?

After doing this basic model, you might try some adding some predictors to your model, like the square footage or age of the home. You might also try using the log of the sales price as the target.

Finally, try instead of using a binary variable for before or after to use a tpost variable incicating the number of years before or after the development that the sale took place. Do your conclusions change?

**Stretch Goals:** 
Modify your code so that it works on other developments. Are your findings the same? 

Next, rather than focusing on a single development at time, modify your model to consider all housing developments. Note that you'll likely want to include the sales year as an explanatory variable in your model.

**Bonus:** [Assessing the Impact of Affordable Housing on Nearby Property Values in Alexandria, Virginia](https://www.urban.org/research/publication/assessing-impact-affordable-housing-nearby-property-values-alexandria-virginia) also looks at the impact of affordable housing developments on nearby property values, but uses a different model which focuses only on homes that were sold both before and after the development was placed in service. Use a similar setup to analyze the data from Davidson County.
