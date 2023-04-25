---
{"dg-publish":true,"dg-path":"garden/This is the way.md","permalink":"/garden/this-is-the-way/"}
---


# this is the way

## heading

mando no 5

[[90 Outputs/93 Digital Garden/Digitial Garden Test 2\|Digitial Garden Test 2]]

> [!NOTE] Note title
> Information

## Reading

``` dataview
TABLE WITHOUT ID

("[[" + file.name + "|" + Title + "]]") AS Title,
Author,
publish-date AS "Publish date",
("![coverImg|100](" + Cover + ")") as Cover,
rating AS "Rating",
Recommender,
Comment,
Date,
URL

FROM "99 Old/Backlog/60 Indexes/62 Books"

WHERE State = "reading"

SORT Title
```
