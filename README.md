# FSM
Fraxinus Survival and Mortality Model (version 0.3)

Provides probabilities and likelihood of mortality of street and park ash trees exposed to emerald ash borer

To run: Load the FSMmodel.R script into R Console. Change working directory to location of data in CSV format. Make sure this is a copy of data because the script will modify the file adding columns! Run function FSM(fname), where fname is the file name (without extension and in " "). You can set which model type, threshold for defining mortality, producing mortality year prediction, and displaying some basic output information. These and their defaults are described below.

## data format
Data should be organized in a CSV file with trees in rows (tree10000.csv is an example data set with 10,000 trees). The function will add mortality probability, mortality prediction (0,1 based on a threshold), and mortality year (1-3 after data year, not included by default) columns to the data file. Required data for models vary, however, bark splits and DBH are required for all models. 

Tree = unique tree ID

BS = presence/absence of bark splits (1/0)

DBH = diameter at breast height (cm)

DB = percent crown dieback (5-100%)

V = vigor rating (1-5, with 1 = healthiest and 5 = crown half dead)

WP = presence/absence of woodpecker activity (1/0)

## type = Model variables to include ("dieback", "vigor", "woodpecker")
Three model types are available each includes presence of bark splits (1,0) and diameter at breast height (DBH, in cm) ("dieback", "vigor", "woodpecker"). 

Default type is "dieback", which provides model output using inputs of percent dieback, DBH, and bark splits. Published model had 83.8% correct prediction of mortality.

Type "vigor" provides model output using inputs of vigor, DBH, and bark splits. Published model had 86.5% correct prediction of mortality.

Type "woodpecker" provides model output using inputs of wood pecker activity, DBH, and bark splits. Published model had 75.7% correct prediction of mortality.

## threshold = Probability of mortality that will define if a tree dies within 3 years (continuous 0-1)
Default threshold is 0.65

## year = Model to predict the year after data collection year in which a tree will die (TRUE, FALSE)
Default year is FALSE (year=FALSE) because it requires percent dieback and DBH. Published model had 71.6% correct prediction of mortality year.

## display = Output basic statistics from trees, including counts, means of input variables, mean probability of mortality, for trees that will survive, die, and total (based on threshold of mortality value). (TRUE, FALSE)
Default display is TRUE (display=TRUE)

Clark, RE, KN Boyes, LE Morgan, AJ Storer, and JM Marshall. 2015. Development and assessment of ash mortality models in relation to emerald ash borer infestation. Arboriculture & Urban Forestry 41, 270-278. (<a href="http://joa.isa-arbor.com/request.asp?JournalID=1&ArticleID=3370&Type=2">article</a>)
