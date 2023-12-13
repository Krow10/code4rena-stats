# code4rena-stats

Charts and statistical insights for [Code4rena](https://code4rena.com).

## How to run

You can use [nbviewer](https://nbviewer.org/github/Krow10/code4rena-stats/tree/main/) or [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/Krow10/code4rena-stats/HEAD) to run the notebooks online.

You can also `git clone git@github.com:Krow10/code4rena-stats.git` and run [JupyterLab](https://jupyter.org/) for running them locally.

## Notebooks

- `findings`: value ($USD) of findings over time, by category, etc.
- `trends`: trying to predict future trends in the Code4rena space.
- `wardens`: warden's participation over time, rewards, etc.

## Data

Data is pulled from the [community resources](https://github.com/code-423n4/code423n4.com/blob/main/_data/README-community_resources.md) given by Code4rena. There are two main `.csv` files that are regularly updated with new contests. My [older project](https://github.com/Krow10/code4rena-scraper) used to scrape additional data from GitHub and the Code4rena [website](https://code4rena.com), but this is not necessarily needed anymore.

**findings.csv**

|contest|handle|finding|risk|score|pie|split|slice|award|awardCoin|awardUSD|
|-------|------|-------|----|-----|---|-----|-----|-----|---------|--------|
|Contest ID|Name of the warden (or team)|Finding ID with risk prefix|Risk level as integer|*?*|Number of shares for the finding[^1]|Number of identical submissions for the finding[^1]|Number of shares assigned to the warden's finding[^1]|$shares*\frac{pot}{number of shares}$[^1]|Coin used for the reward|Converted coin *amount* to $USD|

[^1]: From [Code4rena docs](https://docs.code4rena.com/awarding/incentive-model-and-awards/curve-logic)

**contests.csv**

|contestid|title|sponsor|details|start_time|end_time|amount|repo|findingsRepo|hide|league|
|---------|-----|-------|-------|----------|--------|------|----|------------|----|------|
|Contest ID|Contest title|Contest sponsor|Summary of project|Start time for contest in date time format (e.g. Wed Feb 17 2021 00:00:00 GMT+0000)|End time for contest in date time format|Total prize pool for the contest|GitHub repo of the project|GitHub repo for submissions to contest|Used to hide contest from showing on the website|Mostly blockchain identifier for the project|