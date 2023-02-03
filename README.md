# blurlscraper
A bash script that scrapes blog urls from sitemaps and alerts you in Slack when there's a new blog in the list!

# Usage:

## Create a list of clients/company names

cat client.txt 
```
client1
client2
client3
client4
```

## Create new directories for each client with a sitemapurl.txt file which include the url for the sitemap (https://www.example.com/sitemap.xml)

Your directory should look something like this:

```
.
├── blurlscraper
├── clients.txt
├── client1
│   └── sitemapurl.txt
├── client2
│   └── sitemapurl.txt
├── client3
│   └── sitemapurl.txt
└── client4
    └── sitemapurl.txt
```
NOTE: You will need to search for the correct sitemap for each website manually. Check the robots.txt file for each site and make sure they have then links to the blogs in them.

# Usage

## Give execute permissions to blurlscraper

`chmod +x ./blurlscraper`

Execute blurlscraper

`./blurlscraper`

## Once your run this your files should something look like this:

```
.
├── blogreader.py
├── blurlscraper
├── clients.txt
├── client1
│   ├── blogmap.xml
│   ├── blogurls.txt
│   ├── sitemap.xml
│   └── sitemapurl.txt
├── client2
│   ├── blogmap.xml
│   ├── blogurls.txt
│   ├── sitemap.xml
│   └── sitemapurl.txt
├── client3
│   ├── blogmap.xml
│   ├── blogurls.txt
│   ├── sitemap.xml
│   └── sitemapurl.txt
└── client4
    ├── blogmap.xml
    ├── blogurls.txt
    ├── sitemap.xml
    └── sitemapurl.txt
    
```
## When you run the script again

When you run this script again the script will compare the results with the previous scan and send an alert to your slack channel! This will create a new file called `blogurls.old.txt` to store the previous scan results. 

If any differences are discovered between the old and new scan you will get an alert in Slack that looks like this:


```
client1 has posted a new blog:

https://client1.com/blog/newblogurl
```






