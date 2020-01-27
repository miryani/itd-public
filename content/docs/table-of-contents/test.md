---
title: "Test"
date: 2020-01-24T17:28:04-06:00
draft: true
---
$scratch := newScratch
$scratch.Set "greeting" "Hello"


TEST DATE
{{ .Scratch.Get "greeting" }}
.AddDate YEARS MONTHS DAYS


---
.date
---


- Created: 20444-01-24T11:25:00-06:00
- Created: "{{ .date }}"


- .date {{ .PublishDate.Format }} {{.Date "Jan 2nd 2006"}} {{ <time>{{ now.date }}</time> }}
- .date
- .Date {{ $.Page.Params.PublishDate }}
