---
Creator: Nick
categories:
  - Blog  
tags:
  - Politics
---
In the 2020 democratic presidential primary, there was an influx of candidates, with each claiming only they had the power to beat Donald Trump. Of the [29](https://en.wikipedia.org/wiki/2020_Democratic_Party_presidential_primaries) total candidates, 12 were running while currently serving in Congress (during the 116th session, which [ran from](https://www.senate.gov/legislative/DatesofSessionsofCongress.htm) January 3rd, 2019 to January 3rd 2021, excluding recesses). Of the [237 democrats in the House and 48 in the Senate](https://fas.org/sgp/crs/misc/R45583.pdf) (including independents who caucus with the democrats), around 4.2% were running for Congress. This is potentially impactful to congressional activity, as 0% of Republicans in Congress were running, and many of the Democrats were influential figures. This post is meant to analyze the Congressional actions of these 12 presidential candidates during their time running for the nomination. By comparing this period (and the 116th congress as a whole, when most candidates began their campaign) to other periods in Congress, we can attempt to understand the impact running for president has on the congressional activity of those candidates. However, we will not analyze trends of broad congressional action during the average campaign period, leaving that to future posts/articles.

See [my Jupyter Notebook for the code for this post (and further exploratory analysis)](/Congressional Statements Analysis.html)

## A Look at the Data
Using the [ProPublica Congress API](https://projects.propublica.org/api-docs/congress-api/), I isolated the presidential candidates who were currently in Congress and used different metrics to compare them as a group over time. Usually, I compare their time as presidential candidates to their past (and future) selves, so as best to measure campaign-caused changes. The main question this post attempts to answer is this: to what extent do members of Congress running for president abdicate their congressional duties or otherwise alter congressional behavior during their campaigns? I attempt to use a variety of proxies, such as congressional statements, introduced bills, and various voting statistics to answer this question.

### Statements
Congressional statements, mainly in the form of press releases, are ways for members of Congress to communicate their opinions on bills or other political situations to their constituents or to the broader public. These statements can get picked up by the media and potentially amplify someone's image. One may expect a presidential candidate in Congress to increase press releases, so as to exhibit their important role in policymaking. However, candidates may also choose to focus on other avenues--e.g., through a candidate's social media page or through press releases by their presidential campaigns--instead of through Congress. In my opinion, an increase in congressional statements doesn't necessarily correspond with an increase in congressional focus, but a decrease in statements may signify a decreased focus (on congressional affairs as a whole, as perhaps a candidate is occupying their time writing/lobbying for specific bills). If one is using their congressional platform less, they are necessarily less focused on congressional issues, though they may be more attentive to the US political landscape as a whole. However, this reasoning is pure speculation and should in no way be taken as how members of Congress act without sufficient analysis.
![Presidential candidates total statements by month](\..\images\pres-candidates-graphs\statements_total_by_cand.png)

For almost all the candidates, the total number of congressional statements per month during their presidential campaigns was reasonably similar to that of other periods. For a few candidates (Gabbard, Warren, Klobuchar, Delaney) there appeared to be a spike in congressional statements soon after their campaign announcements. For some (Gabbard, Sanders), statements have a generally downward trend. Nothing seems conclusive here; each candidate has a different trend and much of the intra-campaign-period numbers fit with the rest of the non-campaign data. It's entirely possible that the fluctuations in the total number of statements is explained by exogenous political phenomena; however, in that case we'd expect a greater correlation between statement spikes among candidates. What I believe is more likely is that each candidate has a different media strategy, and some believed press releases, i.e., congressional statements/announcements of congressional actions, would best attract attention from the media (if they even took this into consideration at all).

<!-- **ADD LINE OF BEST FIT???**
GET TYPES OF STATEMENTS????
also highlight recesses???-->


### Bills
The main duty of Congress is to legislate. Introducing bills is a crucial part of the job of a member of Congress. During a presidential run, observers may expect candidates to focus on campaigning rather than legislating. However, not all presidential candidates are members of Congress, thus it may be wise for the candidates who are to use their position to their advantage. Through bills, candidates serving in Congress could educate voters about meaningful legislation that corresponds with the political message they want to send. Here, we examine the number of total bills introduced every month, again highlighting the duration of each candidate's presidential run.
![Presidential candidates total bills introduced by month](\..\images\pres-candidates-graphs\bills_introduced.png)

For many candidates (Klobuchar, Sanders, Gillibrand, Ryan, Delaney), the months around the beginning of the campaign coincide with a spike in the total number of bills introduced per month. Though [many of these bills won't be passed](https://www.govtrack.us/congress/bills/statistics), they can generate attention, and members of Congress can blame the incumbent or opposing party when their grand, utopian bill dies in Congress. In a breakout moment in one of the democratic debates, Sanders told a fellow candidate that he ["wrote the damn bill"](https://www.vox.com/policy-and-politics/2019/7/31/20748428/bernie-sanders-democratic-debate-wrote-damn-bill), in reference to a Medicare-for-all proposal. These moments give members of Congress legitimacy that non-congressional based candidates may lack. Though bills need to be introduced significantly before the campaign starts to have a chance of passing, as stump speech fodder alone they could attract serious publicity; e.g., [https://www.rollcall.com/2019/03/08/house-passes-hr-1-government-overhaul-sending-it-back-to-campaign-trail/](HR 1, a large voting reform bill, passed the House at the beginning of Session 116 and could be referenced on the campaign trail as a way to show what Democrats stood for). Though candidates generally release specific legislative plans through their presidential campaigns, I see no reason why they wouldn't introduce something similar in Congress as a bill. Usually, candidates can capitalize on mature bills showing bipartisanship or a focus on issues deemed important during the election. Therefore, if a member of Congress' only goal was to boost their legislative status for a future presidential run, we may expect more bills to be introduced in the year or so leading up to the beginning of presidential campaigns rather than within the period of presidential campaigns themselves. However, this assumption is unrealistic, as members of Congress have a vast array of competing interests they need to satisfy, inside of which it could be hard to fit preparation for (what is for many) a longshot presidential run.

Yet, when campaigning starts, Congressional records will be re-examined and many may feel pressured to shield against accusations of legislative inaction by introducing new bills. As the quality of introduced bills isn't portrayed in the visualization, it's possible that members of Congress with lower than average total bill introduction numbers could still be using bill introduction as a way to make a difference in their presidential campaigns. Some candidates may choose to focus on a handful of meaningful bills instead of introducing as many as possible. Yet a congressmember can't realistically get their bill through committee and then the broader legislative body in a matter of months, especially when focusing on a campaign. By introducing bills during a campaign, candidates can reveal their legislative priorities to voters; on the campaign trial, they can observe what many voters want and introduce a bill to deal with it, hopefully recruiting some undecided voters along the way.

However, I doubt that bill introduction is an important part of campaigning. The analysis given above is likely naïve, and only portrays what I believe are possible explanations for variations in bill introduction data.

Though we may expect members of Congress to be focused on legislating during their presidential runs, these data show that with respect to bill introduction, members of Congress seem just as active while running--if not more--than during any other time frame.

### Votes
Voting is another crucial duty of Congress. Therefore, I will be looking at aggregate voting statistics by congressional session (as I couldn't find monthly statistics in the Propublica API).

#### Missed Votes
First, missed votes are an important gauge of how focused a member of Congress may be on their legislative duties. If they decide to spend a lot of time outside the chamber, it will correspond to missed votes. Here, I expect the presidential candidates to miss more votes during their campaign periods.
![Presidential candidates missed votes percent](\..\images\pres-candidates-graphs\missed_votes.png)

Predictably, this seems the most consequential statistic yet. Session 116 was a significant change for all of the presidential candidates in Congress in terms of missed votes. However, perhaps it was due to Covid-19, which intersected with the last year of this congressional session. To determine if this was the case, let's look at the average percent of missed votes for different groups in Congress).
<img src="\..\images\pres-candidates-graphs\missed_votes_summary.png" alt="Percent missed votes summary" class="smaller-img">

Covid-19 doesn't seem to have had that large of an impact... The average missed votes percentage are similar for each session shown. Based on this graph, it's safe to say that these presidential candidates missed votes in Session 116 at a significantly higher rate than regular members of Congress. See [GovTrack](https://www.govtrack.us/congress/votes/presidential-candidates) for a more complete analysis across years, parties, and presidential campaigns.

#### Votes with/against Party
One may expect presidential candidates to vote more with their party preceding a presidential run as they try to please the voters in their entire party instead of in their specific congressional district or state. However, a candidate may also find success in voting against their party in an attempt to better differentiate themselves from other candidates, especially in a large field like the 2020 Democratic primary. Because it's easier to visualize the percentage of votes against one's party than votes for one's party (as the former's percentages are smaller), I will display the former. The percent votes against one's party is defined as the percentage of votes where the member of congress voted against the majority of their party in their respective chamber--e.g., from [Propublica](https://projects.propublica.org/represent/members/W000817/votes-against-party/116), "Sen. Warren voted against a majority of Senate Democrats 92 times (21.2%) in the 116th Congress (2019-20)."
![Presidential candidates votes against party percent](\..\images\pres-candidates-graphs\against_party_votes.png)

These results seem mixed; in Session 116, some candidates appeared to take the former strategy, siding more than usual/the same amount with other Democrats, while others increased their against-party vote percentage. Let's again look at mean vote percentages to come to a better conclusion.
<img src="\..\images\pres-candidates-graphs\against_party_summary.png" alt="Percent votes against party summary" class="smaller-img">

It seems that the presidential candidates were more apt to vote against their party than other Democrats in both Sessions 115 and 116. A plausible explanation could be that those who decided to become presidential candidates were the ones who developed the most individualism in the age of Trump. Perhaps the candidates didn't start voting more against their party because they wanted to differentiate themselves but instead because they believed their party was going in the wrong direction after Trump was elected and they could best redirect its path. Perhaps it's notable that the more successful candidates (Warren, Klobuchar, Sanders) had a greater percentage of votes against their party; however, Booker, Gillibrand, and Harris also share this distinction and none of them excelled. Further dividing the analysis into chambers may be more helpful; all of the candidates just mentioned were Senators, who can typically be more independent from their party without the same consequences faced by House members. While Senators appear to have higher absolute percentage votes against party, they also have higher relative percentage votes against party in Session 116 (and occasionally in 115 as well). All presidential candidates from the House (Gabbard, Ryan, Swalwell, Moulton) decreased their percentage of against-party votes in Session 116. Perhaps this was due to Republicans controlling the House, meaning individual members had less sway, unable to afford opposing the party. Yet, Republicans had control in Session 113 and all of the House members mentioned had a relatively higher percentage of votes against party in that session. So, to see if presidential candidates truly differ in their percentage of against-party votes, we must split our data by legislative body.

<img src="\..\images\pres-candidates-graphs\chamber_against_party_summary.png" alt="Percent votes against party summary by chamber" class="full-img">

Presidential candidates serving in the House seem to have about the same average trends as other House Democrats, while candidates serving in the Senate diverge from the other Senate Democrats in Sessions 115 and 116 by around 5% and 7.5% respectively, which is enough to appear significant. Therefore, it seems Senators running for president can use their independent status to vote against party lines, making them stand out in ways House candidates cannot.

Looking at broad trends, these data reveal that House Democrats have tended to vote less and less against their party, while Senate Democrats have done the opposite (excluding Session 117). Future analysis could reveal the significance behind these changes; perhaps the greater polarization described by the media manifests itself in solidarity among each party in the House. Then, the disagreement lives in the Senate, as seen with [increasing votes for cloture](https://qz.com/1413228/what-is-a-cloture-vote-and-why-is-mcconnell-is-using-it-for-the-kavanaugh-vote/) and [Democrats' increasing frustration with the filibuster](https://apnews.com/article/donald-trump-filibusters-gun-politics-government-and-politics-93c53b3aa8d2b91d3c2d5884f3cdf139). As someone interested in politics but not entangled within it (or with a great knowledge of it), most legislative news I hear comes from the Senate. The House can pass whatever they want, but in our current environment, the Senate is where bills can live or die. As someone fairly new to the political scene, I wonder if it was always like this.

In Session 117, the current congressional session, Democrat percent votes against party are miniscule compared to the percentage in the other sessions shown, reflecting a unity among the Democrats not seen in years. With Democrats in both chambers of Congress conforming to their party's ideas, the future looks good for Biden's presidency. However, such a coalition is unlikely to hold for long. With only a quarter of Session 117 complete, there's plenty of time left for Democrats to start bickering and shatter the fragile arrangements they have within their party. But who knows...

*\*\*\* Note: In all the above graphs, "Democrats" does not include Sanders*
<!-- PUT SPACE BETWEEN HEADERS in CSS?
<br />
<br />
<br /> -->

<!-- ## Campaign Finance Analysis
As it's widely known that you need money to succeed in politics, I'll look at the difference in fundraising for these candidates over time (both for congressional and presidential runs) and compare it with their success as a candidate.

### Individual contributions
First, I'll look at total individual contributions for each candidate's presidential and congressional runs. There are two types of individual contributions: itemized contributions, where donors give over $200, and unitemized contributions, where donors give less. For the former, donors must be reported; for the latter, it's not required. (See [this post](https://blog.actblue.com/2020/01/29/the-small-dollar-donors-guide-to-fec-filings/) for more details). One would expect more contributions in both categories for a presidential run. However, by further comparing presidential and congressional fundraising, we may be able to see how much momentum a candidate generated--both from normal people and the wealthier--or how much they outperformed pre-race expectations. While comparing totals, it's important to note the differences in each congressmember's fundraising base. For example, Sanders was immensely popular in his presidential run, yet relatively doesn't raise that much for his Senate campaigns. The presidential to total congressional ratio tells us how well each member leveraged their relations on the Hill, with the media, and with potential donors to expand their voter base.


Itemized:
![Total itemized contributions for 2020 presidential run and all congressional runs](\..\images\pres-candidates-graphs\fec_one_ind_itemized.png)
![Total itemized contributions presidential to congressional ratio](\..\images\pres-candidates-graphs\itemized_pres_cong_ratio.png)

Unitemized:
![Total unitemized contributions for 2020 presidential run and all congressional runs](\..\images\pres-candidates-graphs\fec_one_ind_unitemized.png)
![Total unitemized contributions presidential to congressional ratio](\..\images\pres-candidates-graphs\unitemized_pres_cong_ratio.png)

Also, we can check the ratio of itemized to unitemized contributions for both presidential and congressional campaigns.

Do higher fundraisers in Congress tend to make presidential runs? For this, we must look across time at many presidential elections. However, for now, we will retain our focus on 2020.

Is there an upward trend in fundraising? -->

## Recap
Relative to other candidates, presidential hopefuls serving in Congress are closest to Washington and thus may seem best positioned to benefit from their job. Besides the lofty change in missed votes, none of the data I've shown has revealed a broad abdication of duty or a grand connection between the strategy or characteristics of presidential candidates serving in Congress. There are many reasons why a member of Congress' voting records may change across sessions--e.g., a change in the opinion of their constituents or in their fundraising--as is there reasons for differences in all the other data I've shown. Much of this has likely already been covered in media and detailed academic reports by people who know what they're talking about; however, viewing these data in simple terms helps illuminate basic ideas about congressional functions, not requiring too math-heavy or focused an analysis to understand. Overall, I've revealed some interesting properties of those pursuing the 2020 Democratic presidential nomination while serving in Congress. Perhaps these data show something unifying about the candidates. But realistically, how much do members of Congress care about the number of bills they introduce or press releases they put out? Much of that will be out of their minds, placed in the hands of trusted advisors or otherwise happening naturally as they embark on a journey that they hope ends in the presidency. Still, those advisors and candidate actions must have a strategy, which is one I hoped to glimpse with my analysis.
<!-- Perhaps in the future, I could analyze the total number of statements or bills introduced based on important congressional election dates. -->

<!-- TODO: Get total contributions for a congressional election cycle
i.e. 2 yrs for the house and 6 yrs for the senate (total),
then compare with presidential fundraising. For the latter step,
find out what everything in FEC df means, e.g. net operating expenditures, etc.

use PEW or GALLUP! research, research, research

also, ask how often in debates do candidates mention their bills? somehow research this?

grammar -- congressmember? two words? capitalized? also, "I" vs. "We"
change font on summary bar graphs to match?-->
