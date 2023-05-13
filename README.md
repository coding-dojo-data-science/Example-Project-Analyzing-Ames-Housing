# Example-Project-Analyzing-Ames-Housing
Example Data Science Project Following CRISP-DM Workflow

# Introduction

<center><img src="https://raw.githubusercontent.com/coding-dojo-data-science/Example-Project-Analyzing-Ames-Housing/main/Images/house-image.png" width=800px>

<a href="https://dolinskigroup.com/buy-home/sellers-concessions">Image Source</a></center>

We've been hired by a group of homeowners who are concerned about the value of their homes decreasing before they sell them. They have asked us to take the raw house price data from their hometown, Ames, Iowa to be able to give them data-driven recommendations on how to best increase the value of their home.

We will be following the CRISP-DM workflow for our analysis.  

<center>
<img src="https://lh4.googleusercontent.com/XTLCxAnBAFkfjmtM0twmmqvvRLNFaxKdQlfyQXLn8RCQYiEhzSztw_xH68HcxB6MAnXyzZ-2Zz9gDHFQn2sfuwZJoSGxAurKHOfkmIYbrrXYjXGr1oXxpe_QY-cn7Fz3fJ-sIfXKaM7U1EAuCdq1FFo" width=600px>


<a href="https://www.datascience-pm.com/crisp-dm-2">Image Source</a></center>


<a name='phase1'></a>
## Phase 1) Business Understanding

**Our stakeholders are:**
- People who already own homes in Ames, Iowa

**Their primary goal is:**
- Increase the resale value of their homes.

**They plan to:**
- Modify/renovate their homes based on our analysis.

**What do they need/expect?**
- Actionable insights/recommendations for which modifications they can make to increase the price of their homes.

<a name='phase2'></a>
## Phase 2) Data Understanding


### 2.1) What data have we been provided?



<p>The stakeholders have provided us with two links:</p>
<ul><li> <a href="https://drive.google.com/file/d/1Jach7HsZVywhJnUJmkyqje52ho_0VJgo/view?usp=sharing" target="_blank">Share URL to a .csv file</a> <ul><li>A spreadsheet of various features of homes in their town, as well as the price of the house at the time of sale. </li></ul></li><li><a href="https://docs.google.com/document/d/1nmnel7g35aMOl0mKiSsTHXT8wRzbJ1EktKNqYFEmpWE/edit?usp=sharing" target="_blank">A Data Dictionary File</a><ul><li>A data dictionary is a document that lists the name and explanation for every feature in a dataset.</li></ul></li></ul>
<p>(Note, this is a modified version of the original Ames Iowa Housing dataset found on <a href="https://www.kaggle.com/datasets/marcopale/housing" target="_blank">Kaggle</a>)</p>


# Data Dictionary:

<div><h3>Data Dictionary</h3><ul><li>SalePrice - the property's sale price in dollars. This is the target variable that you're trying to predict for this challenge.</li><li>MSZoning: Identifies the general zoning classification of the sale.<ul>
<li>A Agriculture</li>
<li>C Commercial</li>
<li>FV Floating Village Residential</li>
<li>I Industrial</li>
<li>RH Residential High Density</li>
<li>RL Residential Low Density</li>
<li>RP Residential Low Density Park</li>
<li>RM Residential Medium Density</li></ul></li><li>LotFrontage: Linear feet of street connected to property</li><li>LotArea: Lot size in square feet</li><li>Street: Type of road access to property<ul>
<li>Grvl Gravel</li>
<li>Pave Paved</li></ul></li><li>Alley: Type of alley access to property<ul>
<li>Grvl Gravel</li>
<li>Pave Paved</li>
<li>NA No alley access</li></ul></li><li>Utilities: Type of utilities available<ul>
<li>AllPub All public Utilities (E,G,W,&amp; S)</li>
<li>NoSewr Electricity, Gas, and Water (Septic Tank)</li>
<li>NoSeWa Electricity and Gas Only</li>
<li>ELO Electricity only</li></ul></li><li>Neighborhood: Physical locations within Ames city limits<ul>
<li>Blmngtn Bloomington Heights</li>
<li>Blueste Bluestem</li>
<li>BrDale Briardale</li>
<li>BrkSide Brookside</li>
<li>ClearCr Clear Creek</li>
<li>CollgCr College Creek</li>
<li>Crawfor Crawford</li>
<li>Edwards Edwards</li>
<li>Gilbert Gilbert</li>
<li>IDOTRR Iowa DOT and Rail Road</li>
<li>MeadowV Meadow Village</li>
<li>Mitchel Mitchell</li>
<li>Names North Ames</li>
<li>NoRidge Northridge</li>
<li>NPkVill Northpark Villa</li>
<li>NridgHt Northridge Heights</li>
<li>NWAmes Northwest Ames</li>
<li>OldTown Old Town</li>
<li>SWISU South &amp; West of Iowa State University</li>
<li>Sawyer Sawyer</li>
<li>SawyerW Sawyer West</li>
<li>Somerst Somerset</li>
<li>StoneBr Stone Brook</li>
<li>Timber Timberland</li>
<li>Veenker Veenker</li></ul></li><li>BldgType: Type of dwelling<ul>
<li>1Fam Single-family Detached</li>
<li>2FmCon Two-family Conversion; originally built as one-family dwelling</li>
<li>Duplx Duplex</li>
<li>TwnhsE Townhouse End Unit</li>
<li>TwnhsI Townhouse Inside Unit</li></ul></li><li>HouseStyle: Style of dwelling<ul>
<li>1Story One story</li>
<li>1.5Fin One and one-half story: 2nd level finished</li>
<li>1.5Unf One and one-half story: 2nd level unfinished</li>
<li>2Story Two story</li>
<li>2.5Fin Two and one-half story: 2nd level finished</li>
<li>2.5Unf Two and one-half story: 2nd level unfinished</li>
<li>SFoyer Split Foyer</li>
<li>SLvl Split Level</li></ul></li><li>OverallQual: Overall material and finish quality<ul>
<li>10 Very Excellent</li>
<li>9 Excellent</li>
<li>8 Very Good</li>
<li>7 Good</li>
<li>6 Above Average</li>
<li>5 Average</li>
<li>4 Below Average</li>
<li>3 Fair</li>
<li>2 Poor</li>
<li>1 Very Poor</li></ul></li><li>OverallCond: Overall condition rating<ul>
<li>10 Very Excellent</li>
<li>9 Excellent</li>
<li>8 Very Good</li>
<li>7 Good</li>
<li>6 Above Average</li>
<li>5 Average</li>
<li>4 Below Average</li>
<li>3 Fair</li>
<li>2 Poor</li>
<li>1 Very Poor</li></ul></li><li>YearBuilt: Original construction date</li><li>YearRemodAdd: Remodel date (same as construction date if no remodeling or additions)</li><li>ExterQual: Exterior material quality<ul>
<li>Ex Excellent</li>
<li>Gd Good</li>
<li>TA Average/Typical</li>
<li>Fa Fair</li>
<li>Po Poor</li></ul></li><li>ExterCond: Present condition of the material on the exterior<ul>
<li>Ex Excellent</li>
<li>Gd Good</li>
<li>TA Average/Typical</li>
<li>Fa Fair</li>
<li>Po Poor</li></ul></li><li>BsmtUnfSF: Unfinished square feet of basement area</li><li>TotalBsmtSF: Total square feet of basement area</li><li>CentralAir: Central air conditioning<ul>
<li>N No</li>
<li>Y Yes</li></ul></li><li>GrLivArea: Above grade (ground) living area square feet</li><li>BsmtFullBath: Basement full bathrooms</li><li>BsmtHalfBath: Basement half bathrooms</li><li>FullBath: Full bathrooms above grade</li><li>HalfBath: Half baths above grade</li><li>Bedroom: Number of bedrooms above basement level</li><li>Kitchen: Number of kitchens</li><li>KitchenQual: Kitchen quality<ul>
<li>Ex Excellent</li>
<li>Gd Good</li>
<li>TA Typical/Average</li>
<li>Fa Fair</li>
<li>Po Poor</li></ul></li><li>TotRmsAbvGrd: Total rooms above grade (does not include bathrooms)</li><li>GarageType: Garage location<ul>
<li>2Types More than one type of garage</li>
<li>Attchd Attached to home</li>
<li>Basment Basement Garage</li>
<li>BuiltIn Built-In (Garage part of house - typically has room above garage)</li>
<li>CarPort Car Port</li>
<li>Detchd Detached from home</li>
<li>NA No Garage</li></ul></li><li>GarageYrBlt: Year garage was built</li><li>GarageCars: Size of garage in car capacity</li><li>GarageArea: Size of garage in square feet</li><li>GarageQual: Garage quality<ul>
<li>Ex Excellent</li>
<li>Gd Good</li>
<li>TA Typical/Average</li>
<li>Fa Fair</li>
<li>Po Poor</li>
<li>NA No Garage</li></ul></li><li>GarageCond: Garage condition<ul>
<li>Ex Excellent</li>
<li>Gd Good</li>
<li>TA Typical/Average</li>
<li>Fa Fair</li>
<li>Po Poor</li>
<li>NA No Garage</li></ul></li><li>PavedDrive: Paved driveway<ul>
<li>Y Paved</li>
<li>P Partial Pavement</li>
<li>N Dirt/Gravel</li></ul></li><li>Fence: Fence quality<ul>
<li>GdPrv Good Privacy</li>
<li>MnPrv Minimum Privacy</li>
<li>GdWo Good Wood</li>
<li>MnWw Minimum Wood/Wire</li>
<li>NA No Fence</li></ul></li></ul></div>

