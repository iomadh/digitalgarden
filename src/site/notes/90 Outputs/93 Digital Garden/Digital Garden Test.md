---
{"dg-publish":true,"dg-path":"Digital Garden Test.md","permalink":"/digital-garden-test/","tags":["gardenEntry"],"dg-note-properties":{"created":"2023-04-25 18:01","updated":"2025-01-04 22:42"}}
---


```base
filters:
  and:
    - file.folder == "50 Play/54 Media/54.05 Book Database"
formulas:
  complete%: ((currentPage/pages)*100).round()
views:
  - type: table
    name: Books
    order:
      - file.name
      - bookGenre
      - bookFormat
      - author
      - bookSource
      - bookType
      - currentPage
      - pages
      - listeningTime
      - currentTime
      - rating
  - type: cards
    name: Reading
    filters:
      and:
        - readingState == ["reading"]
        - '!bookFormat.contains("audiobook")'
    order:
      - file.name
      - currentPage
      - formula.complete%
    image: note.Cover
    imageAspectRatio: 1
    imageFit: contain
  - type: cards
    name: Listening
    filters:
      and:
        - readingState == ["reading"]
        - bookFormat == ["audiobook"]
    order:
      - file.name
      - bookGenre
      - bookType
      - listeningTime
      - currentTime
    sort:
      - property: updated
        direction: ASC
    image: note.Cover
    imageFit: contain
  - type: table
    name: Books (Author)
    filters:
      and:
        - author == this
    order:
      - file.name
      - bookGenre
      - bookFormat
      - bookSource
      - bookType
      - pages
      - listeningTime
      - rating
      - finishedDate
    sort:
      - property: finishedDate
        direction: ASC
    columnSize:
      file.name: 221
  - type: table
    name: New Books
    filters:
      or:
        - readingState.contains("new")
        - readingState.isEmpty()
    groupBy:
      property: bookType
      direction: ASC
    order:
      - file.name
      - author
      - bookType
      - bookGenre
      - bookFormat
      - bookSource
      - pages
      - listeningTime
      - readingState
      - seriesTitle
      - seriesNumber
    sort:
      - property: file.ctime
        direction: ASC
    columnSize:
      note.bookGenre: 235
      note.seriesTitle: 230
  - type: table
    name: Unread
    filters:
      and:
        - readingState.contains("unread")
    groupBy:
      property: bookFormat
      direction: ASC
    order:
      - file.name
      - bookGenre
      - bookFormat
      - author
      - bookSource
      - bookType
      - Cover
      - currentPage
      - pages
      - listeningTime
      - currentTime
      - readingState
    sort:
      - property: bookType
        direction: ASC
      - property: AddedDate
        direction: ASC
  - type: table
    name: Next Up
    filters:
      and:
        - readingState.contains("next-up")
    groupBy:
      property: bookFormat
      direction: ASC
    order:
      - file.name
      - bookGenre
      - bookFormat
      - author
      - bookSource
      - bookType
      - Cover
      - currentPage
      - pages
      - listeningTime
      - currentTime
      - readingState
    sort:
      - property: bookType
        direction: ASC
      - property: AddedDate
        direction: ASC
  - type: table
    name: Completed 2025
    filters:
      and:
        - finishedDate >= "2025-01-01"
        - finishedDate <= "2025-12-31"
    order:
      - file.name
      - bookGenre
      - bookFormat
      - author
      - bookType
      - rating
      - finishedDate
    sort:
      - property: finishedDate
        direction: ASC
    columnSize:
      note.bookGenre: 177
      note.author: 173
  - type: table
    name: Completed 2026
    filters:
      and:
        - finishedDate >= "2026-01-01"
    order:
      - file.name
      - bookGenre
      - bookFormat
      - author
      - bookType
      - rating
      - finishedDate
    sort:
      - property: finishedDate
        direction: ASC
    columnSize:
      note.bookGenre: 177
      note.author: 173
  - type: table
    name: Abandoned
    filters:
      and:
        - readingState.contains("abandoned")
    groupBy:
      property: bookFormat
      direction: ASC
    order:
      - file.name
      - bookGenre
      - bookFormat
      - author
      - bookSource
      - bookType
      - Cover
      - currentPage
      - pages
      - listeningTime
      - currentTime
      - readingState
      - startedDate
    sort:
      - property: bookType
        direction: ASC
      - property: AddedDate
        direction: ASC
  - type: table
    name: Series
    filters:
      and:
        - seriesTitle == "The Murderbot Diaries"
    order:
      - file.name
      - bookFormat
      - author
      - bookSource
      - bookType
      - pages
      - rating
      - seriesTitle
      - seriesNumber
      - listeningTime
    sort:
      - property: seriesNumber
        direction: ASC
    columnSize:
      note.author: 118
  - type: table
    name: Books (Author Specific)
    filters:
      and:
        - author == link("Martha Wells")
    order:
      - file.name
      - bookGenre
      - bookFormat
      - bookSource
      - bookType
      - pages
      - listeningTime
      - rating
      - finishedDate
    sort:
      - property: finishedDate
        direction: ASC
    columnSize:
      file.name: 221

```

Currently reading 2 - [[90 Outputs/93 Digital Garden/This is the way\|This is the way]]

| Title | Author | Publish date | Cover | Rating | URL |
| ----- | ------ | ------------ | ----- | ------ | --- |

{ .block-language-dataview}
