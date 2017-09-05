# Monitor with ELK

prepared by Andy Chen

---

## Agenda

* Current Challenge
* ELK Stack
* Kibana
* Dashboard
<!-- * Exception -->
* Q&A

---

## Current Challenge

* Server issue
* Network issue
* Functional issue
* Analytic and debugging

Note:
Server : memory/cpu high  
Network : can not connect to partner or internal server.  
Functional : Login, Register, Placebet, Performance high  
Analytic : Check single member activity  
Debug : We debug issue by logs but we have 20 more servers, time comsuming, now only seconds to search logs.

---

## ELK STACK

![alt text](img/elk-monitor/elk-stack.jpg "Logo Title Text 1")

---

## [Kibana](http://indexing.ez-188bet.com)

* Time Range
* Auto Refresh
* Filter

Note:
Brief intro each sidebar menu in Kibana

---

## Dashboard - [Website]

[Website]: http://indexing.ez-188bet.com/app/kibana#/dashboard/82b00830-8882-11e7-b101-a55a6ab87c69?_g=(refreshInterval:(display:Off,pause:!f,value:0),time:(from:now-7d,mode:quick,to:now))&_a=(description:'Able%20to%20see%20the%20most%20important%20event',filters:!(('$state':(store:appState),meta:(alias:!n,disabled:!f,index:'188-member-application-*',key:index_prefix.keyword,negate:!f,params:!('188-member-application'),type:phrases,value:'188-member-application'),query:(bool:(minimum_should_match:1,should:!((match_phrase:(index_prefix.keyword:'188-member-application'))))))),options:(darkTheme:!f),panels:!((col:1,id:'25eb5900-8888-11e7-80a4-b132e9007906',panelIndex:1,row:1,size_x:6,size_y:3,type:visualization),(col:7,id:'02172240-88b8-11e7-80b1-cf243b756cdc',panelIndex:3,row:1,size_x:6,size_y:3,type:visualization),(col:7,id:'2e93c750-88be-11e7-80b1-cf243b756cdc',panelIndex:4,row:4,size_x:6,size_y:3,type:visualization),(col:1,id:'71825580-8cac-11e7-809d-896037bfe9ff',panelIndex:7,row:4,size_x:6,size_y:3,type:visualization),(col:1,id:'06e3b930-91f2-11e7-92f0-4db8bcfb8b94',panelIndex:8,row:7,size_x:6,size_y:3,type:visualization)),query:(query_string:(analyze_wildcard:!t,query:'*')),timeRestore:!f,title:'%5B188%5D%5Bmember%5D%5Ball%5D%20monitor',uiState:(P-1:(vis:(legendOpen:!f)),P-3:(spy:(mode:(fill:!f,name:!n)),vis:(legendOpen:!f)),P-4:(vis:(legendOpen:!f))),viewMode:edit)

* Register
* Login
* Unique member
Note:
MemberCode, Feature

===

## Dashboard - [SPI]

[SPI]: http://indexing.ez-188bet.com/app/kibana#/dashboard/d16cb5a0-91ff-11e7-9785-f5cff3484362

* Bet Placement
* Bet Settlement
* Authentication Status

===

## Dashboard - [MobileApp]

[MobileApp]: http://elk.chinanorth.cloudapp.chinacloudapi.cn/app/kibana#/dashboard/843b8c70-9191-11e7-8bf0-cb4ecfcce099?_g=(refreshInterval:(display:Off,pause:!f,value:0),time:(from:now-4h,interval:'1h',mode:quick,timezone:Asia%2FShanghai,to:now))&_a=(filters:!(),options:(darkTheme:!f),panels:!((col:7,id:'4b959870-9191-11e7-8bf0-cb4ecfcce099',panelIndex:1,row:1,size_x:6,size_y:3,type:visualization),(col:1,id:c012b8a0-9190-11e7-8bf0-cb4ecfcce099,panelIndex:2,row:1,size_x:6,size_y:3,type:visualization),(col:1,id:'69790100-9192-11e7-8bf0-cb4ecfcce099',panelIndex:3,row:4,size_x:6,size_y:3,type:visualization)),query:(query_string:(analyze_wildcard:!t,query:'*')),timeRestore:!f,title:'%5B188%5D%5Bmobileapp%5D%20monitor',uiState:(),viewMode:view)

* Login performance
* Overall performance

===

## Additional - [Page Views]
[Page Views]: http://indexing.ez-188bet.com/app/kibana#/dashboard/e38e6050-8d48-11e7-8582-49d62553d29a?_g=(refreshInterval:(display:'1%20minute',pause:!f,section:2,value:60000),time:(from:now-12h,mode:quick,to:now))&_a=(description:'',filters:!(('$state':(store:appState),meta:(alias:PageVeiw,disabled:!f,index:'188-member-application-*',key:logger,negate:!f,type:phrase,value:PageBaseController),query:(match:(logger:(query:PageBaseController,type:phrase))))),options:(darkTheme:!f),panels:!((col:6,id:c1cff030-8d36-11e7-8be7-65f5f1696438,panelIndex:1,row:1,size_x:3,size_y:4,type:visualization),(col:1,id:'5d111340-8d36-11e7-a820-9d55ed6f9df1',panelIndex:2,row:1,size_x:5,size_y:2,type:visualization),(col:1,id:b1a9ae40-8d35-11e7-a820-9d55ed6f9df1,panelIndex:3,row:5,size_x:8,size_y:4,type:visualization),(col:9,id:d0661c40-8d37-11e7-8be7-65f5f1696438,panelIndex:4,row:1,size_x:4,size_y:4,type:visualization),(col:9,id:'22e6c0d0-8d44-11e7-8be7-65f5f1696438',panelIndex:5,row:5,size_x:4,size_y:4,type:visualization),(col:1,id:'0385ffb0-8d46-11e7-8be7-65f5f1696438',panelIndex:6,row:3,size_x:5,size_y:2,type:visualization),(col:9,id:'9d459dc0-8d43-11e7-8be7-65f5f1696438',panelIndex:7,row:9,size_x:4,size_y:5,type:visualization),(col:1,id:'1808b690-8d4a-11e7-8be7-65f5f1696438',panelIndex:8,row:9,size_x:8,size_y:5,type:visualization)),query:(query_string:(analyze_wildcard:!t,query:'*')),timeRestore:!t,title:'%5B188%5D%5BDashboard%5D%5BMEM%5D%20Pages%20View',uiState:(P-1:(spy:(mode:(fill:!f,name:!n))),P-2:(vis:(defaultColors:('0%20-%20100':'rgb(0,104,55)'))),P-4:(spy:(mode:(fill:!f,name:!n))),P-5:(spy:(mode:(fill:!f,name:!n)),vis:(legendOpen:!f)),P-6:(spy:(mode:(fill:!f,name:!n)),vis:(legendOpen:!f)),P-7:(vis:(params:(sort:(columnIndex:!n,direction:!n)))),P-8:(mapCenter:!(30.29701788337205,97.646484375),mapZoom:3)),viewMode:view)

---

## Issue or attack

* Login and Register [fail peak], membercode stay same
* Performance peak

[fail peak]: http://indexing.ez-188bet.com/app/kibana#/dashboard/82b00830-8882-11e7-b101-a55a6ab87c69?_g=(refreshInterval:(display:'1%20minute',pause:!f,section:2,value:60000),time:(from:'2017-08-24T16:00:00.000Z',mode:absolute,to:'2017-08-25T15:59:59.999Z'))&_a=(description:'Able%20to%20see%20the%20most%20important%20event',filters:!(),options:(darkTheme:!f),panels:!((col:1,id:'25eb5900-8888-11e7-80a4-b132e9007906',panelIndex:1,row:1,size_x:4,size_y:3,type:visualization),(col:5,id:'02172240-88b8-11e7-80b1-cf243b756cdc',panelIndex:3,row:1,size_x:4,size_y:3,type:visualization),(col:1,id:'2e93c750-88be-11e7-80b1-cf243b756cdc',panelIndex:4,row:4,size_x:4,size_y:3,type:visualization),(col:5,id:f53559c0-88b2-11e7-80b1-cf243b756cdc,panelIndex:6,row:4,size_x:5,size_y:3,type:visualization),(col:9,id:'71825580-8cac-11e7-809d-896037bfe9ff',panelIndex:7,row:1,size_x:4,size_y:3,type:visualization),(col:10,id:'22e6c0d0-8d44-11e7-8be7-65f5f1696438',panelIndex:8,row:4,size_x:3,size_y:3,type:visualization)),query:(query_string:(analyze_wildcard:!t,query:'*')),timeRestore:!f,title:'%5B188%5D%5Bmember%5D%5Ball%5D%5Bmain%20dashboard%5D',uiState:(P-1:(vis:(legendOpen:!f)),P-3:(spy:(mode:(fill:!f,name:!n)),vis:(legendOpen:!f)),P-4:(vis:(legendOpen:!f)),P-6:(spy:(mode:(fill:!f,name:!n)),vis:(defaultColors:('0%20-%204999':'rgb(165,0,38)','10000%20-%201000000000':'rgb(0,104,55)','5000%20-%209999':'rgb(255,255,190)'),legendOpen:!f)),P-8:(spy:(mode:(fill:!f,name:!n)),vis:(legendOpen:!f))),viewMode:view)

---

## ELK limitation

* Base on logs
* [Hardware](http://indexing.ez-188bet.com/app/monitoring)

Note:
If you need more infomation like region, you need to change code and deploy.

---

## Q & A

---

## Thank you