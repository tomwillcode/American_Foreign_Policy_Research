**American Foreign Policy Research**

The purpose of this github repository is to research American Foreign Policy and take a data-driven view into what determines who America deems an ally or an adversary. Obviously there has been a lot of back and forth about what drives American Foreign Policy. Thinkers like Noam Chomsky have posited that America is primarily concerned with defending it's own interests and/or a particular capitalist world-order in a fairly egoist manner. Various liberal and neo-conservative thinkers have posited that American foreign policy is primarily geared towards defending liberal democracy, rule of law, and human rights abroad in a manner that is decidedly principled and not egoist. 

**Overview**
I mined data from several sources pertaining to the countries of the world in 1970. I built a dataframe that classifies countries as US allies (entente/non-aggression/defense) or not, and tracks those countries on many other variables including what type of regime they'd be classified as. Using the Rpart library in R, the following classification tree was created. At the first node, the classification tree differentiates regimes that are democracies or under military rule from all other regime types. For democracies and regimes under military rule, they need only score higher than 1.9 on Ownership of Banks, for America to make an alliance with them. For all other regime types, they must have a government consumption rating of 7.9, which means they must have very low government consumption in order for America to make an alliance with them. 

![A decision tree for determining allies](https://github.com/tomwillcode/American_Foreign_Policy_Research/blob/research/smart_tree.jpg?raw=true)

Below is an overview of performance on training and test data:

![Decision Tree performance](https://github.com/tomwillcode/American_Foreign_Policy_Research/blob/research/smart_tree_performance.jpg?raw=true)

Indeed The tree performs fairly well on training and test data. 

It can be seen that there is a substantial discrepency between the regimes of the world in 1970:

**Regimes of the world in 1970**

![regimes of the world](https://github.com/tomwillcode/American_Foreign_Policy_Research/blob/research/regimes_of_world_70.jpg?raw=true)

And the regimes that the US made an alliance with:

**Regimes of US allies in 1970**

![regimes the us made an alliance with](https://github.com/tomwillcode/American_Foreign_Policy_Research/blob/research/regime_us_allies_70.jpg?raw=true)

However, private ownership of banks sharply discriminated countries the US had alligned with from those they had not:

![Ownership of banks](https://github.com/tomwillcode/American_Foreign_Policy_Research/blob/research/bank_ownership_alliance.jpg?raw=true)

In the end this data-driven model indicates that the qualitative political aspect of a country is the most important variable in deciding whether or not the US will make an alliance with that country. The US showed a clear preference towards democracies, and although they didn't make an alliance with the majority of countries under military rule, they made an alliance with a sizable minority of them. The US made very few alliances with other regime types, but the extent to which a country had a more privatized political economy seemed to be a deciding factor in whether or not the US would align with them.  

**Methodology**
The CSV's were obtained from the sources as described in the next section. The CSV's were all merged and all data-wrangling took place in the Jupyter Notebooks included in the root of this repository. To review that data-wrangling you can view the Jupyter Notbooks:

-Extracting_data_on_regime_type.ipynb

-Extracting politics data.ipynb

-Merge_data_from_Frasier_&_V-Dem.ipynb

-Integrating Alliance Data.ipynb

-Merging_with_Regime_type_data.ipynb

The end product of that data-wrangling is a CSV that contains data on every country in the world in 1970 including political variables from varieties of democracy, economic and political variables from the Frasier Institute, a variable tracking whether or not they were in an alliance with the U.S. and a variable classifying them as one kind or another regime (political regimes of the world dataset). Feel free to review the notebooks, and clone the repository and change something.


In the Analysis folder you will find the data-analysis carried out in R-studio. A PCA was done in the R-notebook "PCA_on_predictors_of_US_alignment.Rmd" to get an idea of what components explain most of the variability in the dataset, and to see which variables load the highest onto those components. The predictive model was built in the R-notebook "Predicting_USA_alliance.Rmd". Feel free to review, clone, change.


**Data Sources**

The following data-sets are used for this project:

-Varieties of Democracy from Our World in Data
https://github.com/owid/notebooks/tree/main/BastianHerre/democracy
https://ourworldindata.org/democracy

-The economic freedom dataset from the Frasier Institute *only for 1970 so far*
https://www.fraserinstitute.org/economic-freedom/dataset?geozone=world&page=dataset&min-year=2&max-year=0&filter=0&year=1970&sort-field=legalSystemsPropertyRights&sort-reversed=1

-Formal Alliances from Correlates of War
https://correlatesofwar.org/data-sets/formal-alliances/

-Political Regimes of the World Dataset, v.2.0, Anckar, Carsten; Fredriksson, Cecilia, 2020, "Political Regimes of the World Dataset, v.2.0", https://doi.org/10.7910/DVN/7SSSAH, Harvard Dataverse, V2, UNF:6:R6ZGXOA4YiGEhOHHK7fdMA== [fileUNF]
https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/7SSSAH

**Merging Data**

All data was merged in a way that is open-source/open access as can be seen in the Jupyter Notebooks in this repository. The dataset that has been created makes a note of whether or not America had become proper allies with a country by the end of 1970, and various predictors from Frasier Inst, and Varieties of Democracy measuring those countries characteristics in the year 1970 are included. It may be a limitation that the predictors aren't from earlier but the Frasier Inst data which is very high-resolution only goes back to 1970.

