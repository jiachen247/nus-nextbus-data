# nus-nextbus-data
data sources for nus nextbus app


1. https://nextbus.comfortdelgro.com.sg/
2. http://www.nus.edu.sg/oca/Transport/Getting-around-NUS.html 
3. http://datamall2.mytransport.sg/ltaodataservice/BusServices?$skip=500


4. Missing infomation


# Tables

## Stops

Column | Type | Options | Remarks
--- | --- | --- | ---
id | int | Auto Increment | Primary Key 
ICode | String | Uniq indexed | Internal Bus Stop Code "name" eg. UHALL
ECode | String | Uniq  indexed | eg. "16199"
Caption | String | | source 1
Description | String | | todo : give stops more desciptive and accurate names  
RoadName | String | | 
Latitude | Double | | 
longitude | Double

## IService
Column | Type | OPtions |  Remarks
--- | --- | --- | ---
ServiceCode | String | PK | 
Express | Boolean | | 
Frequency | String | FK|
OperatingHours | String | FK | 
Remarks | String | | optional 

## IOperatingHours
ServiceGroup | String | PK | 
WeekdayFirst | | | 
WeekdayLast  | | |
SatFirst | | |
SatLast | | |
SunPhFirst | | |
SunPhLast | | |

## IFrequency
Column | Type | Options | Remarks
--- | --- | --- | ---
ServiceGroup | String | FK CK |
Chronology | Int | CK | order of timings
TimeRange | String | eg. "0715-0900"
Peak | Boolean |
Semester | Boolean | CK | 
Weekday | String | |
Saturday | String | |
SundayPh | String | |

## IRoute

Column | Type | Options | Remarks
--- | --- | --- | ---
ServiceCode | String | CK |
remarks | String| |
StopCode | String | CK |  
StopNumber | Int | |
Remarks | | |

## EService
Column | Type | Options | Remarks
--- | --- | --- | ---
ServiceCode | String | PK | eg. "151"
Direction | Int | | 1 or 2 (only 1 for loop services)
StartPoint | String | |
EndPoint | String | | 
AmPeakFrequency | String | |
AmOffPeakFrequency | String | |
PmPeakFrequency | String | |
PmOffPeakFrequency | String | |
...

## ERoute
Column | Type | Options | Remarks
--- | --- | --- | ---
ServiceCode | String | CK | 
Direction | String | CK |
BusStopCode | String | CK | 
WeekdayFirstBus | String | | 
WeekdayLastBus | String | | 
SatFirstBus| String | | 
SatLastBus | String | | 
SunFirstBus | String | | 
SunLastBus | String | | 

http://datamall2.mytransport.sg/ltaodataservice/BusRoutes?$skip=23000



