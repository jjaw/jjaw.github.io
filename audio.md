---
layout: default
---

## Title of Audio File One

*Description of the File*
  _Testing out Space_
  

## Title of Audio File Two

*Description of the File*

* What we did here
* Item 2
  * Item 2a
```javascript
 function callNumbers(column) {
  
  // Call the Numbers API for random math fact
  
  var name = "";
  
  for (var i = 2; i <=16; i++) {
  
  var name2 = SpreadsheetApp.getActive().getSheetByName('data').getRange('A' + i).getValue();
  var url = "https://api.coinmarketcap.com/v1/ticker/" + name2;
  var sheet = SpreadsheetApp.getActive().getSheetByName('data');
  var response = UrlFetchApp.fetch(url);
  
  var json = response.getContentText();
  var data = JSON.parse(json);
  
  //Logger.log(data["Markets"]);
  Logger.log(data[0]["price_usd"]);
  
  
  //Market Cap of the crypto in cell B
  sheet.getRange('B' + i).setValue(data[0]["market_cap_usd"]);
  
  //USD value of the crypto in cell C
  sheet.getRange('C' + i).setValue(data[0]["price_usd"]);
  
  
  
  //SpreadsheetApp.getActiveSheet().getRange('F2').setValue(data[0]["price_usd"]);
  //https://www.worldcoinindex.com/apiservice/json?key={BAiC69zvfldkCoBNYh8o1DCem}
}
}
```
