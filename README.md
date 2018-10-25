# pdaHW3

1. In the first homework, you examined the relationship between pain and time for 200 individuals in the weather dataset. You also examined the correlation between pain and temperature. You then looked at the relationships between the intercepts and slopes from the regression and factors that varied by patient such as age and sex. This forms the basis of a multilevel model in which pain varies within patient according to time and temperature and between patients these relationships vary with patient-level factors. In this exercise, you will put these together and fit a multilevel model in which within patient, pain is a function of time and temperature and between patients these relationships may depend on age, race, income, treatment, sex,  occupation, working status and use of NSAIDs. Use the lme or lmer function to fit a multilevel model in which

 

Yit = ai + biXit + eit

 

ai = g0 + g1zi + ui

bi = h0 + h1zi + wi

 

where Yit = pain at time t for individual i, Xit = time t or temperature at time t for individual i

 zi= patient level factor (age, sex, race, income, occupation, working status, use of NSAIDs

 

Build a multivariable regression model treating ai and bi  as random effects. Make sure to give a thorough writeup of your results with appropriate graphs and tables. Code should be put at the end of the assignment.

 

The syntax for lmer is lmer(y~1+x+(1+x|Cluster), data = …) where y is the response variable, x are the fixed effects (predictors) and (1+x|Cluster) describes the random effects nested within cluster. 

 

 

2. Use the text files srrs2.txt and cty.txt found in the Datasets folder to analyze the radon data in order to determine factors that affect the amount of radon measured in houses randomly sampled in various counties in Minnesota as a function of the floor on which the measurement was taken, the uranium level of the county, whether or not the house has a basement and whether or not the home is single family. First use only the Minnesota data. In this case you will constuct a 2 level model for 1) houses within counties with predictors that correspond to variables measured on houses and 2) counties with the county level predictor uranium. Use a logarithmic transformation of both radon and uranium. The file radon text files.rtf contains a codebook but key variables are described below also.

 

Srrs2.txt includes data from houses sampled within states and counties with one row per house. The key variables that you will need are:

 

idnum: House number

state2: State (don't use state) Arizona (AZ), Indiana (IN), Massachusetts (MA), Michigan (MI), Minnesota (MN), Missouri (MO), North Dakota (ND), Pennsylvania (PA) and Wisconsin (WI)

stfips: state number (used in setting up variables)

typebldg: = 1 if single family; otherwise another type of home (lump all others together

floor: floor of house on which radon measurement taken (0 = basement, 1 = 1st, etc.; 9 indicates missing)

basement: Y if house has basement; N if house does not have basement; else unknown

activity: radon level

county: name of county

cntyfips: county number (used in setting up variables)

 

Cty.txt includes data on county uranium levels. You will need the following variables:

stfips: state number code

ctfips: county number code

st: state

cty: county

uppm: average uranium level in county

 

Note that there are some additional variables you can ignore and that some of these variables might have a few additional categories that you will have to determine what to do with. For instance, there are a few homes where readings were not taken on the basement or first floors but on the second or third. You could choose to treat these as non-basement (grouping with first floor for example).

 

You will first need to create a dataset that has the following variables:

 

House, State, County Single family house (1/0), Basement (1/0), Floor of house. Activity. Uranium level

 

Note that not all counties and states in the cty.txt data are in the srrs2.txt dataset.

 

Once the dataset is created (for hints on how to do this check out the Gelman/Hill R files saved in the Rscripts folder particularly 12.2 and 12.6) 

 

Explain which factors are related to the radon levels and construct some useful tables and figures to explain your model.

 

3. (Extra credit but required for PhD students). Expand your model to 3 levels by considering all of the states. Level 1 is not house within county within state; level 2 is county within state and level 3 is state (there are no state level variables). 