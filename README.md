**American Foreign Policy Research**

The purpose of this github repository is to research American Foreign Policy and take a data-driven view into what determines who America deems an ally or an adversary. Obviously there has been a lot of back and forth about what drives American Foreign Policy. Thinkers like Noam Chomsky have posited that America is primarily concerned with defending it's own interests and/or a particular capitalist world-order in a fairly egoist manner. Various liberal and neo-conservative thinkers have posited that American foreign policy is primarily geared towards defending liberal democracy, rule of law, and human rights abroad in a manner that is decidedly principled and not egoist. 

**Data Sources**

The following data-sets are used for this project:

-Varieties of Democracy from Our World in Data
https://github.com/owid/notebooks/tree/main/BastianHerre/democracy
https://ourworldindata.org/democracy

-The economic freedom dataset from the Frasier Institute *only for 1970 so far*
https://www.fraserinstitute.org/economic-freedom/dataset?geozone=world&page=dataset&min-year=2&max-year=0&filter=0&year=1970&sort-field=legalSystemsPropertyRights&sort-reversed=1

-Formal Alliances from Correlates of War
https://correlatesofwar.org/data-sets/formal-alliances/

**Merging Data**

All data was merged in a way that is open-source/open access as can be seen in the Jupyter Notebooks in this repository. The dataset that has been created makes a note of whether or not America had become proper allies with a country by the end of 1970, and various predictors from Frasier Inst, and Varieties of Democracy measuring those countries characteristics in the year 1970 are included. It may be a limitation that the predictors aren't from earlier but the Frasier Inst data which is very high-resolution only goes back to 1970.

**PCA Analysis**

So far a PCA has been carried out in R-Studio to understand what the main principle components are amongst the variables that will be used as predictors, so that a few predictors can be used that are the most promising in terms of their ability to represent the data. A "two-factor" solution seems to fit the predictors best. One factor separates capitalist-liberal democracies from countries that are not, and the second factor is related to the overall size and power of government especially from an economic standpoint. 
