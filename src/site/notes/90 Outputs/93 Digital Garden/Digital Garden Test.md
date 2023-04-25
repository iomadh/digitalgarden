---
{"dg-publish":true,"dg-path":"garden/Digital Garden Test.md","permalink":"/garden/digital-garden-test/","tags":["gardenEntry"]}
---


Hello World updated - [[90 Outputs/93 Digital Garden/This is the way\|This is the way]]

``` dataview
TABLE WITHOUT ID link(file.link, fstitle) as "Articles", dateformat(file.ctime, "dd MMM yy") as "CreatedDate", readingtime as Time
from "99 Old/Review"
where file.name != "_indexOf_2. fsReview"
sort file.ctime 
```