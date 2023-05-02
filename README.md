# TDF_Data

## Background
In 2017 I spent some time scraping and collating the results data of the Tour de France. I was learning how to use PowerBI and was excited by the web-scraping capabilities. The TdF website had HTML tables at the time but didn't contain the length of stages (in km). I obtained this from the [Bike Race Info](https://www.bikeraceinfo.com/) website using regular expressions. 
There are other websites available such as [Pro Cycling Stats](https://www.procyclingstats.com/race/tour-de-france/) that provide this information now. However, as the Power Query code I used is long since defunct I thought it might be helpful to make JSON data available should anyone like to access it. I'll give a summary of table structures below. The Tour de France website changed in 2018, breaking my queries so I haven't updated since then. 

## Notes
There may be errors in the data set. I have done as much error checking as possible but essentially this was a very large query that ran for a long time. Depending on the way data was recorded, there are blanks. For example, only in later years is the holder of the green/polka/white jersey recorded throughout the tournament. 
I have split the riders data table according to year due to file size restrictions.

### Years.json

Heading |  Notes
--- | --- 
Year | The year of the race
Total Distance | The overall distance of that year's race
Average Speed | The average winning speed of that year's race
Average Stage Length | The average stage length, in kilometres
Winner | The name of the winner of that year's race
Second Place | The name of the runner up of that year's race
Yellow Jersey | The name of the winner of the yellow jersey (same as winner)
Green Jersey | The name of the winner of the green jersey
Red Polka Dot Jersey | The name of the winner of the polka dot jersey
White Jersey | The name of the winner of the white jersey

### Riders*.json

Heading |  Notes
--- | --- 
Stage-ID | Code that can be used to link stages between tables
Year | The year of the race
Position | The position of that rider at the end of the stage
Rider Name | The name of the rider
Rider Number | The rider's jersey number
Rider speed on stage | Calculated rider speed on stage *errors noted*
Rider Time Gap | A string denoting the rider's gap behind leader on stage
Rider Time Gap (s) | The time gap in seconds

### Stages.json

Heading |  Notes
--- | --- 
Stage-ID | Code that can be used to link stages between tables
Date | The date when the stage was held
Year | The year of the race
Stage Name | The name of the stage
Stage Number | The stage number in that year's race
Start Location | The name of the location where the stage started
Stage Distance | The distance of the stage in kilometres
Finish Location | The name of the location where the stage finished
Is Final Stage | Boolean denoting whether the stage is the final of the tour

### Winners.json

Heading |  Notes
--- | --- 
Stage-ID | Code that can be used to link stages between tables
Year | The year of the race
Stage Number | The stage number
Name | The name of the winner of the stage
Stage Finishing Time | The time taken to finish in __h ' "__ format
Rider Speed on Stage | The average speed of the stage in km/h

### Jerseys.json
Heading |  Notes
--- | ---
Stage-ID | Code that can be used to link stages between tables
Year | The year of the race
Stage Number | The stage number
Yellow Jersey | The name of the hold of the yellow jersey at end of stage
Green Jersey | The name of the holder of the green jersey
Red Polka Dot Jersey | The name of the holder of the polka dot jersey
White Jersey | The name of the holder of the white jersey
