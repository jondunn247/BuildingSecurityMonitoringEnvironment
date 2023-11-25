# BuildingSecurityMonitoringEnvironment
<h2>Description</h2>
Used Splunk to build a custom security monitoring environment for a fictional organization, tested that environment against simulated attacks, and presented your monitoring environment to the class.
<br />


<h2>Utilities Used</h2>

- <b>Splunk</b> 

<h2>Environments Used </h2>

- <b>Vagrant Virtual Machine</b>

   </td>
  </tr>
</table>


## Windows Server Log Questions

**Report Analysis for Severity**



* Did you detect any suspicious changes in severity?

```
% Yes - significant changes in severity level for "high", 6.9% to 20.2% while severity level for Informational decreased from 93.9% to 79.8.

```
<img src= "https://i.imgur.com/XydbNCe.png" height="70%" width="70%" />

<img src= "https://i.imgur.com/M9C8LoO.png" height="70%" width="70%" />


**Report Analysis for Failed Activities**



* Did you detect any suspicious changes in failed activities? 

```
    No, The failure rate dropped from 3.0 to 1.6; my conclusion is that there are no suspicious changes in failed activities.

```

<img src= "https://i.imgur.com/yVkctGM.png" height="70%" width="70%" />

<img src= "https://i.imgur.com/SVu8XrV.png" height="70%" width="70%" />


**Alert Analysis for Failed Windows Activity**


* Did you detect a suspicious volume of failed activity?

```
Yes - suspicious volume of failed activity with events count of 35 on Wednesday, March 25, 2020 at 8:00 AM.

```
<img src= "https://i.imgur.com/NThtRIq.png" height="70%" width="70%" />

<img src= "https://i.imgur.com/JqdWhBv.png" height="70%" width="70%" />

*  If so, what was the count of events in the hour(s) it occurred?

```
35 events
```


*  When did it occur?

```
8:00 AM on Wednesday, March 25, 2020
```


*  Would your alert be triggered for this activity?

```
Yes
```


*  After reviewing, would you change your threshold from what you previously selected?

```
No, the result appears to be isolated and not an indication of a True Negative.
```



   

**Alert Analysis for Successful Logins**



*  Did you detect a suspicious volume of successful logins?

```
Yes

```


*  If so, what was the count of events in the hour(s) it occurred?

```
196 events at 11AM on Wednesday, March 25, 2020
77 events at 12PM on Wednesday, March 25, 2020
```


*  Who is the primary user logging in?

```
user_k
```


*  When did it occur?

```
11AM and 12PM on Wednesday, March 25, 2020
```


*  Would your alert be triggered for this activity?

```
Yes
```


*  After reviewing, would you change your threshold from what you previously selected?

```
No
```



**Alert Analysis for Deleted Accounts**



* Did you detect a suspicious volume of deleted accounts?  

   


```
No

```


**Dashboard Analysis for Time Chart of Signatures**



*    Does anything stand out as suspicious?

```

Yes, there is a significant increase in user accounts being locked out from 1:00 AM - 3:00 AM, attempted password resets from 9:00 AM to 11:00 AM and successful logins from 11:00 AM - 1:00 PM.
```

*    What signatures stand out?

```
A user account was locked out
An attempt was made to reset an accounts password
An account was successfully logged on
```

*    What time did it begin and stop for each signature?

```
A user account was locked out: 1:00 AM - 3:00 AM
An attempt was made to reset an accounts password: 9:00 AM to 11:00 AM
An account was successfully logged on: 11:00 AM - 1:00 PM
```

*    What is the peak count of the different signatures?

```
A user account was locked out: 896
An attempt was made to reset an accounts password: 1258
An account was successfully logged on: 196
```

**Dashboard Analysis for Users  **


*    Does anything stand out as suspicious?

```

User_a, user_k, and user_j have activity levels far above baseline.
```


*    Which users stand out?

```
user_a
user_k
user_j
```


*    What time did it begin and stop for each user?

```
user_a: suspicious activity started 1:00 AM and ended 3:00 AM
user_k: suspicious activity started 9:00 AM and ended 11:00 AM
user_j: suspicious activity started 11:00 AM and ended 1:00 PM
```


*    What is the peak count of the different users?

```
User_a - 984
User_k - 1256
User_j - 196
```
**Dashboard Analysis for Signatures with Bar, Graph, and Pie Charts**

*    Does anything stand out as suspicious?

```

Yes, there is a significant increase in user accounts being locked out, attempted password resets and successful logins.

```
*    Do the results match your findings in your time chart for signatures?    

```
Yes
```

**Dashboard Analysis for Users with Bar, Graph, and Pie Charts  **   


*    Does anything stand out as suspicious?

```

```


*    Do the results match your findings in your time chart for users?

```
Yes
```

**Dashboard Analysis for Users with Statistical Charts**


* What are the advantages and disadvantages of using this report, compared to the other user panels that you created?

```
Using this report has more information in one place, whereas the panels have specific but limited information.
```

## Apache Web Server Log Questions

**Report Analysis for Methods**


*  Did you detect any suspicious changes in HTTP methods? If so, which one?

```
Yes, the GET request method count changed from 9851 to 1357 while the POST method changed from 106 to 1324. And Head changed from 42 to 15.
There was tremendous change in the POST method which jumped from 1% to 29%.

```

* What is that method used for?


```
POST method is used to send data to the server.
```
**Report Analysis for Referrer Domains**

*    Did you detect any suspicious changes in referrer domains?

```
There was a huge drop in the count for http://www.semicomplete.com domain from  3038 to 764. Similarly for http://semicomplete.com one from 2001 to 572.
```

**Report Analysis for HTTP Response Codes**


*  Did you detect any suspicious changes in HTTP response codes? 

```

- On 2020-03-25 at 18:00 there were 624 - 404 response code and the average number of 404 code responses sat around 1-5.
- On 2020-03-25 at 20:00 we had around 1415 -200 response code. The average amount sits around 100-120
```

**Alert Analysis for International Activity**


*  Did you detect a suspicious volume of international activity? 

```
Yes we detect suspicious volume of international activity from Ukraine
```

*  If so, what was the count of the hour(s) it occurred in?

```
The attack was between 7-8PM
```


*  Would your alert be triggered for this activity?

```
Yes the alert would have been triggered for this activity
```


*  After reviewing, would you change the threshold that you previously selected?

```
No, the threshold would not need to be changed from what it currently is.
```

**Alert Analysis for HTTP POST Activity**


*  Did you detect any suspicious volume of HTTP POST activity?

```
Yes, the count for POST activity jumped from 7 to 1296.

```


*  If so, what was the count of the hour(s) it occurred in?

```
Between 7 and 8:00 pm
```

*  When did it occur?

```
Wednesday March 25th 2020, 8:00  PM
```

*  After reviewing, would you change the threshold that you previously selected?  

```
No, except at 8:00 PM the average alerts were below the threshold.
```

**Dashboard Analysis for Time Chart of HTTP Methods**

*  Does anything stand out as suspicious?

```
Yes,
```

*  Which method seems to be used in the attack?

```
POST
```


*  At what times did the attack start and stop?

```
Attack started at 7:00 PM and stopped by 9:00 PM.

```
*  What is the peak count of the top method during the attack?

```
1296
```

**Dashboard Analysis for Cluster Map**

*  Does anything stand out as suspicious?

```
Yes. When looking at the cluster map we were able to see that Ukraine has a suspicious jump in activity.
```

*  Which new location (city, country) on the map has a high volume of activity? (**Hint**: Zoom in on the map.)

```
The country is Ukraine and the two cities are Kiev and Kharkiv
```

*  What is the count of that city?

```
Kiev's number sits at 439 and Kharkiv sits at 433.

```

**Dashboard Analysis for URI Data**

*  Does anything stand out as suspicious?
```
Yes, prior to the attack the top URI was the company homepage followed by 5 pages that were averaging no more than 5% click rate 

```

*  What URI is hit the most?

 ```
1-   /VSI_Account_logon.php 
2– /files/logstash/logstash-1.3.2-monolithic.jar

```


*  Based on the URI being accessed, what could the attacker potentially be doing?

```
The attacker made attempts to brute force VSI's account logon page. The logstash file was also used to collect data from the website and transmitted to another destination.
