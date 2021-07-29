# SouqScraper
Script for scarping items from souq.com using BeautifulSoup and Python3 
you need to install Python3 and BeautifulSoup 

the code is very simple 

```sh
import requests
import urllib.request
import time
from bs4 import BeautifulSoup
import json
import csv
filecsv = open('SouqDataapple.csv', 'w',encoding='utf8')
file = open('SouqDataapple.json','w',encoding='utf8')
# Set the URL you want to webscrape from
url = 'https://URL'
file.write('[\n')
data = {}
csv_columns = ['name','price','img']
for page in range(1000):
    print('---', page, '---')
    r = requests.get(url + str(page))
    print(url + str(page))
    soup = BeautifulSoup(r.content, "html.parser")
    ancher=soup.find_all('div',{'class' : 'column column-block block-grid-large single-item'})
    writer = csv.DictWriter(filecsv, fieldnames=csv_columns)
    i=0
    writer.writeheader()
    for pt in  ancher:        
file.write("\n]")
filecsv.close()
file.close()
```
