# nba_spider

A webcrawler which crawls stats.nba.com for every active players traditional split data.

This crawler creates an automated instance of Chrome, which follows links from stats.nba.com/players/list/ to each individual players traditional split page. From there it saves the data from the most recent season they've participated in, and stores it in a text file named "output.txt". Each row is denoted by player name.


Requirements:

This web cralwer uses several python libraries together to function properly.
> Scrapy  (scrapy.org)
> Selenium   https://pypi.org/project/selenium/)
> Beautifulsoup  (https://www.crummy.com/software/BeautifulSoup/bs4/doc/)

There is a chrome webdriver included in the source files under the /spiders folder, which will be used to create the automated chrome instance. This may seem excessive, but I've found it to be the easiest way to force javascript populated tables to render properly.

This was developed using a python 3.7 venv, and has not been tested using other python versions.

Setup: 

Quick and Easy/Already have Scrapy:
If you already have scrapy, you can create a new project using "scrapy startproject projectname" in your target directory. Once the project has been initialized, nba_spider.py and a chromedriver should be placed in the spiders directory.

Full setup:
First, clone the repository. Then, open it using your desired IDE, assuming it supports python vEnv. Install the plugins required (either manually or using your IDE).

Running:
Once setup is complete use the terminal to navigate to the spiders directory. Then, run the command "scrapy runspider nba_stats.py" if you built the full project, or "scrapy crawl nba_stats.py" if you simply cloned the repository.
