# Auctionator

[deutsche Version](./README_de.md)

Is a web application for auctioning a given sum among a group of people. 

---
## Notes

* [Java](https://java.com/de/download) in version 8 or higher is required.
* The web application was developed especially for a rental auction in a [Mietshaeuser Syndikat](https://www.syndikat.org) housing project. 
* No attention has been paid to universal readiness or comprehensive documentation.
* Subsequent editing of an auction is not intended. Manipulating the SQLite auction file with an external tool (e.g. [SQLiteBrowser](http://sqlitebrowser.org/)) is of course possible.
* See for yourself if you find it useful. Feel free to help us develop it further.


---
## Useage

### Download

[https://github.com/qdev/Auctionator/releases/download/v0.1/auctionator.jar](https://github.com/qdev/Auctionator/releases/download/v0.1/auctionator.jar)

### Create auction file

with: `java -jar auctionator.jar $db_file_name CREATE $money_goal $person1 $person2 $personX`
  
e.g.: `java -jar auctionator.jar auction1.db CREATE 5000 Anne Max 'Alex P.'`
  
This creates in the current directory an auction file named Auktion1.db for 3 bidders with the goal to find 5000 Euro.
  
### Start the Web application

with: `java[-Dserver.port=PORT] -jar auctionator.jar $db_file_name START`
  
Specifying a port is optional. Default is 10042, so the above example is started with: 
  
`java -jar auctionator.jar auction1.db START`
  
### Opening the Web application
  
Open `http://$servername:$port/auction/` in your browser.
  
For our example: `http://localhost:10042/auction/`
  
Individuals can now place their bids there 
  
The last bid always ends the current round and creates a new one.
  
The "ich bin neugierig" button reveals the bids of the other people
  
---
## Hints for developers

* It's a [Maven](https://maven.apache.org/) project  
