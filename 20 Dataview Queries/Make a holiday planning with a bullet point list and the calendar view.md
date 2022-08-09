---
description: Render a event-overview calendar when i.e. planning holidays
---
#dv/calendar #dv/where #dv/flatten #dv/list #dv/sort 

# Make a holiday planning with a bullet point list and the calendar view

## Basic 

> [!warning] Limitations
> This overview calendar comes with two limitations: First, you cannot have any other list (nor task list) inside the file that does _not_ have a "when" field. The calendar won't render then. Secondly: The dot hover will always show you the whole page, instead of the concrete event happening.

- Some cool event [when:: 2022-08-14]
- Some cool event [when:: 2022-08-15]
- Some cool event happening later [when:: 2022-08-19]
- Some cool event happening later [when:: 2022-08-22]
- Some cool event [when:: 2022-08-18]
- Some cool event [when:: 2022-08-19]
- Some cool event [when:: 2022-08-19]
- Some cool event [when:: 2022-08-19]
- Second thing happening on 22th [when:: 2022-08-22]


```dataview
CALENDAR L.when
FROM "Make a holiday planning with a bullet point list and the calendar view"
FLATTEN file.lists AS L
```
It could be helpful to render a chronologically sorted List in addition:

```dataview
LIST WITHOUT ID L.text
FROM "Make a holiday planning with a bullet point list and the calendar view"
FLATTEN file.lists AS L
SORT L.when
```