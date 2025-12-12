# Do Fireballers Make Better Relievers?

**Members:** Nate Petz, Aden Lepp

## Introduction
The general question we set out to answer was whether throwing harder as an MLB reliever makes you a better pitcher. We compared Fastball velocity percentile against a statistic called a **goose egg**. 

In essence, a goose egg is tallied when a reliever doesn’t allow a run in a high-leverage inning. It happens when a pitcher’s lead/deficit is 0, 1, or 2, and in the 7th inning or later and the pitcher gets through the inning without allowing a run. It is an improvement on the save stat, because giving up 2 runs in the 9th up 3 nets a save when that is not really a good outing. It also shows how valuable a setup man is because it rewards throwing shutout innings in the 7th and 8th when the game is tied, or the lead/deficit is 1 run, when previously there existed no stat rewarding such an important appearance. 

We plotted fastball percentile, which we got from `baseballsavant.com`, against this goose egg stat, for which a partial database from 1921-2017 was found on `fivethirtyeight.com`. We had to fill in this database for 2018-2025 because fastball tracking didn’t begin as accessibly until 2015, and we wanted the data up to the current picture.

## Methods
The data preparation is really the meat of the project. We had to run a Python script on all play-by-play data from 2018-2025 to finish the goose egg data, and the merging of the two dataframes was quite complicated. Specifically, the merge was difficult because the goose egg data didn’t have player IDs to match up with our percentile rankings for 2018-2025, so we had to read in an additional file and merge it with our data so that the player IDs matched. 

Then we plotted that data along with a line of best fit to see if there is a correlation. The 2021 data shows what appears to be a positive correlation between fastball velocity and goose eggs, with all players above 30 goose eggs also being above the 65th percentile for fastball velocity.
<iframe src="goose_egg_plot.html" height="600" width="100%" frameBorder="0"></iframe>
*Figure 1: Plot for 2021. Fastball velocity percentile is labeled on the x-axis (0-100) and the number of goose eggs for the 2021 season is on the y-axis. The regression line has a positive slope, implying that higher fastball velocity correlates with more goose eggs.*

## Conclusions
In each plot, the line of best fit has a positive slope, indicating a positive correlation. This would suggest that harder throwers make better relievers. Our goose egg data from the script followed with gamelogs on `baseballreference.com`, so I have no concerns about the completion of the database. 

The current dataframe that’s used for plotting displays the middle name, last name, which isn’t ideal, but I’m sure it’s an easy fix. I think especially when introducing a new statistic into a sport, it’s really easy to overcomplicate, as many new statistics are expected values or rate-based statistics, but introducing a counting stat is more valuable because it’s more flexible for this kind of analysis. There are opportunities for cluster models, analysis to see which stat in the `baseballsavant` database influences goose eggs the most, it’s really an opportunity for growth as managing and pitching evolve.

---

### Group Assessment
I would say 75-25 me right now but only because we haven’t had time to delve into his aspect which was analysing the gwar stat which compares pitchers against a replacement level reliever.
