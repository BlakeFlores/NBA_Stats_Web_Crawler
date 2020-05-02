# nba_spider

A webcrawler which crawls stats.nba.com for every active players traditional split data.

This crawler creates an automated instance of Chrome, which follows links from stats.nba.com/players/list/ to each individual players traditional split page. From there it saves the data from the most recent season they've participated in, and stores it in a text file named "output.txt". Each row is denoted by player name.


# Requirements:

This web cralwer uses several python libraries together to function properly.
> Scrapy  (scrapy.org)

> Selenium   https://pypi.org/project/selenium/)

> Beautifulsoup  (https://www.crummy.com/software/BeautifulSoup/bs4/doc/)

There is a chrome webdriver included in the source files under the /spiders folder, which will be used to create the automated chrome instance. This may seem excessive, but I've found it to be the easiest way to force javascript populated tables to render properly.

This was developed using a python 3.7 venv, and has not been tested using other python versions.

# Setup: 

Quick and Easy/Already have Scrapy:

If you already have scrapy, you can create a new project using "scrapy startproject projectname" in your target directory. Once the project has been initialized, nba_spider.py and a chromedriver should be placed in the spiders directory.

Full setup:

First, clone the repository. Then, open it using your desired IDE, assuming it supports python vEnv. Install the plugins required (either manually or using your IDE).

# Running:
Once setup is complete use the terminal to navigate to the spiders directory. Then, run the command "scrapy runspider nba_stats.py" if you built the full project, or "scrapy crawl nba_stats.py" if you simply cloned the repository.

The running program should open a chrome window, and open each player stats page in a new tab before scraping the data and closing the tab. There are delays built in intentionally to prevent flooding their servers with requests. 

Player stats will be recorded in the "output_file.txt" file, under the spiders folder.

A video of this web crawler running can be found at: 

https://www.youtube.com/watch?v=7DEtFSkUPEM


# FAQ

Why is this so complicated? Can't one of these three tools (selenium, bs4, scrapy) be enough?
>This started as a scrapy crawler, and had to adopt quite a few changes before useful data could be extracted. The problems I ran into mostly involved javascript. If an actual browswer like  Chrome doesn't accees the webpage, the NBA sites' javascript script will not populate their stats tables with anything but dummy filler values. So, franken-spider was formed to force render the js elements so I can use bs4 to pull the rendered html and scrape useful data.

Isn't there an API for this? Wouldn't that be easier?
>Yes, the NBA has a well developed API for retrieving stats, but this was more about scraping data that was hard to get than the data itself. I don't really care all that much about the NBA, but this stat collection was fun!


Help! I can't get this to run!/I don't understand something
>Feel free to email me at Blake.I.Flores@gmail.com

