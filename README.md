<span style="color:#CC0000"> ___Coca Cola Dispenser Service Cost Prediction___ </span>

<span style="color:#CC0000"> __Service Cost Estimation \- Timeline Summary__ </span>

<span style="color:#CC0000"> __Model 1 | Estimating __ </span>  <span style="color:#666666"> __‘per service’__ </span>  <span style="color:#CC0000"> __ cost using non\-sensor data__ </span>

__Factors fed to the model__

__City__

__Outlet__

__Dispenser Model__

__Avg\. Volume Dispensed__

__Age of Dispenser__

__Time from Last Service__

__Month of Servicing__

__Is there something common between cities/outlets that have high servicing costs?__

__Is the servicing cost significantly impacted by the age & usage of dispenser?__

__Is the servicing cost related to time of the year or the last time the dispenser was serviced?__

<span style="color:#CC0000"> __Model 1 | Low Accuracy but shows high sensitivity to City & Outlet__ </span>

The error in the model was  <span style="color:#CC0000"> __$350__ </span> \. However the the standard deviation of the models itself was  <span style="color:#CC0000"> __$370__ </span> \. Therefore we can infer that the model has  _not been able to learn_  much about estimating cost at a per service level

<span style="color:#CC0000"> _Service Costs are far more correlated with static factors as compared to usage or maintenance patterns\. \(\* Low confidence\)_ </span>

![](img/Coke_Week_Model_27th_June_copy0.png)

![](img/Coke_Week_Model_27th_June_copy1.png)

<span style="color:#CC0000"> __Model 1 | Little to no correlation between top states/cities/outlets__ </span>

<span style="color:#CC0000"> __Top 10 High Service Cost Outlets__ </span>

__Hawaii__

__New York__

__Maine__

__Vermont__

__Antelope__

__Red Bluff__

__Early__

__Zion__

__Rego Park__

__Plex__

__Jones Bros Cupcakes__

__El Meson Of Fl__

__Conico Management__

__United Supermarket Llc__

__Taco Time International__

__Swankys Taco Shop__

__42 North__

__Nemacolin Woodlands__

__Boyne Usa Resorts__

__Papa Joes Dmc__

__Wyoming__

__Iowa__

__Louisiana__

__Alabama__

__Iowa__

__Scottsburg__

__Frostburg__

__Maize__

__Aubrey__

<span style="color:#CC0000"> __Model 1 | High cost outlets incur similar costs in all states __ </span>

__What do we infer?__

There are factors that make the outlet of a brand in one city/state different from that in another city/state\. Intuitively\, these factors could be  __usage behaviour or climate__ \, impact of which may be quantified through  __sensor data\.__

__All Figures in $__

| States | Present In Top 5 States |  | Present in atleast 4 of top 5 states |  |
| :-: | :-: | :-: | :-: | :-: |
|  | Five Guys Enterprises Llc | Wendys International | Moes Southwest Grill Llc | Popeyes Louisiana Kitchen Inc |
| Maine | 213 | 276 | 276 | 216 |
| New York | 519 | 305 | 367 | 517 |
| Hawaii | 499 | 205 | 397 | Not Present |
| Vermont | 256 | 254 | 135 | 278 |
| Rhode Island | 510 | 477 | Not Present | 283 |
| Wyoming | 307 | 223 | Not Present | 207 |
| Iowa | 438 | 458 | 384 | 353 |
| Alabama | 812 | 439 | Not Present | 219 |
| Louisiana | 412 | 263 | 308 | Not Present |
| Nebraska | Not Present | 274 | Not Present | Not Present |

<span style="color:#CC0000"> __Model 1 | ~30% accuracy in predicting the __ </span>  <span style="color:#666666"> __25th percentile cost bucket__ </span>

__Why predict at cost bucket level?__

__The model was unable to predict accurately at __  <span style="color:#CC0000"> __‘per service cost’__ </span>  __\, therefore we tried to __  _reduce the granularity_  __ and estimate the __  <span style="color:#CC0000"> __cost bucket__ </span>  __\. However\, the model is able to predict the cost only with a 30% accuracy\.__

![](img/Coke_Week_Model_27th_June_copy2.png)

![](img/Coke_Week_Model_27th_June_copy3.png)

![](img/Coke_Week_Model_27th_June_copy4.png)

<span style="color:#CC0000"> __Model 1 | ~32% accuracy in predicting the __ </span>  <span style="color:#666666"> __annual service cost for a dispenser__ </span>

__Why predict annual cost?__

__The model was unable to predict accurately at __  <span style="color:#CC0000"> __‘per service cost’ & ‘cost bucket’ __ </span>  __level__  __\, therefore we tried to __  _further reduce the granularity_  __ and estimate the __  <span style="color:#CC0000"> __annual cost__ </span>  __\. However\, the model performance is no different\. The accuracy to predict the top and bottom quartiles also lies within __  __35\-40%__  __\.__

![](img/Coke_Week_Model_27th_June_copy5.png)

![](img/Coke_Week_Model_27th_June_copy6.png)

![](img/Coke_Week_Model_27th_June_copy7.png)

<span style="color:#CC0000"> __Model 1 | Summary__ </span>

The model is unable to predict the servicing cost for a dispenser \- both per service cost or annual cost even at cost bucket level

The cities/states with higher per service cost seem to the one with higher number of dispensers installed\. But at the same time\, the volume dispensed has shows low correlation with service cost\. This means that there are some other factors that we need to consider\.

<span style="color:#CC0000"> __Next Steps \- Model 2__ </span>

To study sensor data and establish its relationship with the service cost of a dispenser

<span style="color:#CC0000"> __Model 2 Dipstick Test | ~40% Accuracy in predicting the annual cost bucket__ </span>

__What do we infer?__

Data coming from sensors such as  __Trouble Count__  may be able to help us predict the cost of servicing better\. More granular error data may help us predict the kind of resolution required and therefore the cost for servicing\.

<span style="color:#CC0000"> _Trouble Add count & Part Removal _ </span>  <span style="color:#CC0000"> _impact the service costs more than other factors such as City\, Outlet\, or State_ </span>

![](img/Coke_Week_Model_27th_June_copy8.png)

![](img/Coke_Week_Model_27th_June_copy9.png)

<span style="color:#CC0000"> __Model 2 Dipstick Test | ~40% Accuracy in predicting the annual cost bucket__ </span>

__What do we infer?__

Data coming from sensors such as Trouble Count may be able to help us predict the cost of servicing better\. More granular error data may help us predict the kind of resolution required and therefore the cost for servicing\.

The performance improves significantly  <span style="color:#CC0000"> __to 55% __ </span> in predicting  _top and bottom quartiles_  \( <span style="color:#CC0000"> __from earlier 35%__ </span> \)

![](img/Coke_Week_Model_27th_June_copy10.png)

![](img/Coke_Week_Model_27th_June_copy11.png)

![](img/Coke_Week_Model_27th_June_copy12.png)

<span style="color:#CC0000"> __What metrics can sensor data help us predict?__ </span>

* __Is there a correlation between the __  __sensor data leading to the service__  __ and the __  __service cost__  __? __
* __Is there a correlation between __  __service cost__  __ and __  __number of hours__  __ involved spent for a service?__
  * _If yes\, can sensor data help us predict the number of hours for a service?_
* __Can we predict the __  __service reason__  __ based on sensor data leading upto the date of service?__
* __\*\* We are using data at individual dispenser level__

<span style="color:#CC0000"> __What metrics can sensor data help us predict?__ </span>

__Predicting cost at work\-order level__

__Predicting cost bucket for a work\-order__

__Hours Spent in a service__

__Reason for Service__

__The data we use to train models is at __  _individual dispenser level_  __\. We will study data from all sensors and try to predict service cost or one of the input metrics for service cost based on that\.__

Sensor data correlation with service cost

<span style="color:#CC0000"> __S9100 | Sensor data improves error by 29% | Reboot count most important__ </span>

__LGBM Model__

__Error: __  <span style="color:#CC0000"> __$250__ </span>  \(down from $350\)

_But still poor\!_

__R Squared: __ 0\.076

_Min Data in leaf: 20_

_Maximum Bins: 1000_

_Categorical Data Handling Enabled_

![](img/Coke_Week_Model_27th_June_copy13.png)

__Top 5 sensor points \-__

Reboot Count

Beverage Unavailable Count

Total Volume

Carb State Change

FCM Pump under delivery

<span style="color:#CC0000"> _Also signalling their correlation with a dispenser requiring service_ </span>

Sensor data correlation with service cost

<span style="color:#CC0000"> __S9000 | No improvement in error | Reboot count most important__ </span>

__LGBM Model__

__Error: __  <span style="color:#CC0000"> __$360__ </span>

__R Squared: __ 0\.13

_Min Data in leaf: 20_

_Maximum Bins: 1000_

_Categorical Data Handling Enabled_

![](img/Coke_Week_Model_27th_June_copy14.png)

__Top 5 sensor points \-__

Reboot Count

Shelf Agitator Home Sensor

Total Volume

Trouble Add

Error Link Lost

<span style="color:#CC0000"> _Also signalling their correlation with a dispenser requiring service_ </span>

Sensor data correlation with service cost

<span style="color:#CC0000"> __~48% accuracy in predicting the cost bucket of a service__ </span>

_Sensor data helps us improve the model performance for Low \(Bottom 30 percentile\) and High \(Top 40 percentile\) Cost Buckets\, but the prediction accuracy _  <span style="color:#CC0000"> _falls below 20%_ </span>  _ for the _  _Medium Cost bucket\._

_Also\, the_  _ parts related sensor data_  _\, significant for each _  _dispenser type_  _\, seems to be different from each other i\.e\.   Carb State and FCM pump for S9100 but Shelf Agitator for S9000_

![](img/Coke_Week_Model_27th_June_copy15.png)

![](img/Coke_Week_Model_27th_June_copy16.png)

Hours Spent correlation with Service Cost

<span style="color:#CC0000"> __Hours spent in service supersede all other input variables__ </span>

Total service cost is very highly dependent on total hour spent for service\. This may be because of hourly service rates and the need for higher hours for certain issues\.

![](img/Coke_Week_Model_27th_June_copy17.png)

![](img/Coke_Week_Model_27th_June_copy18.png)

Hours Spent correlation with Service Cost

<span style="color:#CC0000"> __60% accuracy on including ‘hours spent’ in the model__ </span>

_But hours spent is an output metric\!_  Can we know the hours spent before the service happens?

_Hours spent can have multiple sources of noise such as technician proficiency and service provider\, among others_

![](img/Coke_Week_Model_27th_June_copy19.png)

![](img/Coke_Week_Model_27th_June_copy20.png)

Sensor data correlation with Hours Spent

<span style="color:#CC0000"> __Catboost model | Failed to predict Hours or Cost based on sensor data __ </span>  <span style="color:#4A86E8"> __\(At individual dispenser level\)__ </span>

| Model | Target - Variable | Test RMSE | Test R- squared |
| :-: | :-: | :-: | :-: |
| CatBoost | Cost | 249.3 | 0.084 |
| CatBoost | Hour | 1.12 | 0.094 |

* <span style="color:#CC0000"> __So\,__ </span>
* Sensor data is unable to improve model performance in predicting the cost of service
  * But we can predict the service cost bucket \(especially Top 40 Percentile & Bottom 30 Percentile\)
* We know that the service cost is directly related to the number of hours spent in service\.
  * But sensor data does not help predict the number of hours spent

Sensor data correlation with Service Reason

<span style="color:#CC0000"> __Flow Control and CPM issues seem to have the highest service cost__ </span>

![](img/Coke_Week_Model_27th_June_copy21.png)

_However\, _  <span style="color:#CC0000"> _NO_ </span>  _ correlation was found between the service reason and the hours spent during the service_

Sensor data correlation with Service Reason

<span style="color:#CC0000"> __Sensors’ max\. count shows higher importance in predicting service reason__ </span>

![](img/Coke_Week_Model_27th_June_copy22.png)

Sensor data correlation with Service Reason

<span style="color:#CC0000"> __36% accuracy in predicting the service reason \- based on sensor data __ </span>

| Service Reason | precision | recall | f1-score | support |
| :-: | :-: | :-: | :-: | :-: |
| Drain | 0.27 | 0.56 | 0.37 | 1110 |
| Flow Controls / ECM/Module | 0.49 | 0.67 | 0.57 | 1551 |
| General Customer Issues | 0.16 | 0.04 | 0.06 | 526 |
| General Electrical | 0.28 | 0.1 | 0.15 | 358 |
| Ice Subsystem | 0.19 | 0.01 | 0.02 | 443 |
| NN5 subsystem | 0.28 | 0.15 | 0.2 | 522 |
| Nozzle | 0.21 | 0.04 | 0.07 | 444 |
| other | 0.29 | 0.21 | 0.25 | 939 |
| SPM - Micro-Ingredient | 0.37 | 0.52 | 0.43 | 1088 |
| Special Process | 0.37 | 0.09 | 0.15 | 347 |

<span style="color:#CC0000"> __So\,__ </span>

We are unable to predict the service reason based on sensor data leading to the service\.

<span style="color:#CC0000"> __Significantly better performance on rolling up the output metric to daily cost__ </span>

__Why predict the daily cost?__

__We are unable to predict the service reason\, hours spent\, or cost per service\. And therefore\, we tried reducing the granularity of the model to predict __  _Daily Service Cost per active dispenser\. _  _The _  <span style="color:#CC0000"> _Mean Absolute Percentage Error is ~15%\. _ </span>

<span style="color:#CC0000"> _The significance of specific sensor’s remains in line with what we observed earlier \- _ </span>  _[Link](slide19.xml)_

![](img/Coke_Week_Model_27th_June_copy23.png)

![](img/Coke_Week_Model_27th_June_copy24.png)

<span style="color:#CC0000"> __Model Parameters \- Significant improvement from per service cost models__ </span>

| Parameter | S9000 | S9100 |
| :-: | :-: | :-: |
| Root Mean Squared Error | 0.44 | 0.39 |
| R-Squared | 0.62 | 0.39 |
| MAPE | 0.15 | 0.19 |
| Mean | 2.26 | 1.71 |
| Standard Deviation | 0.75 | 0.52 |

The model analysed same day sensor data to come up with daily service cost per active dispenser\. The results were not better when we tried to use T\-1 or T\-2 data points\. In fact\, the performance of the model deteriorated a bit\.

__This means either \-__

_The time lag between sensor data and service is less than a day\, _  _or_

_Irrespective of day\, the data of all sensors combined remains constant over a period of time _

<span style="color:#CC0000"> __Daily Service cost has very high dependence on the day of the week__ </span>

__Why check dependence on day of the week?__

__The distribution of servicing cost is thin peaked\! And therefore any factor that can help us move our predictions is worth investigating\.__

<span style="color:#CC0000"> _Day of the week shows up as far more important \- Does that mean we don't need anything else? \- _ </span>  _NO_

![](img/Coke_Week_Model_27th_June_copy25.png)

![](img/Coke_Week_Model_27th_June_copy26.png)

<span style="color:#CC0000"> __Weekends have ~3% lesser average cost compared to weekdays__ </span>

| Day | Average Total Cost | Average Parts Cost | # of services |
| :-: | :-: | :-: | :-: |
| Sunday | 282 | 117 | 8345 |
| Monday | 295 | 132 | 20057 |
| Tuesday | 292 | 128 | 18187 |
| Wednesday | 294 | 129 | 17200 |
| Thursday | 298 | 132 | 16675 |
| Friday | 292 | 127 | 17195 |
| Saturday | 277 | 112 | 11133 |

| Parameter | S9000 | S9100 |
| :-: | :-: | :-: |
| Root Mean Squared Error | 0.38 | 0.37 |
| R-Squared | 0.71 | 0.48 |
| MAPE | 0.13 | 0.18 |

_We observe that the weekends have slightly lesser average servicing cost \- _  _Mostly driven by the cost of parts replaced\._  _ _ This may be an outcome of an logistical situation\.

However\, the model improves only by  __~2% points__  and that’s because the standard deviation of average cost by weekday is  __~$7\.6 while the mean is ~$290\,__  and therefore as stated on previous slide\, a very thin peaked distribution\.
