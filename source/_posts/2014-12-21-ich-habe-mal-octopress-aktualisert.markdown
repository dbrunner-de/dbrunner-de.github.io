---
layout: post
title: "Ich habe mal Octopress aktualisert"
date: 2014-12-21 11:58:16 +0000
comments: true
categories: Homepage, Octopress 
description: "Octopress aktualisieren"
keywords: "Octopress, Update, neue Version, Hinweise"
---

Neulich fiel mir auf, dass die Suchfunktion, die auf Google basiert,
nicht nur auf der eigenen Homepage, sondern im "gesamten" Suchindex
von Google gesucht hat. Eben flatterte dieser
[Tweet](https://twitter.com/octopress/status/546528904115404800) an
mir vorbei und da hat sich wohl die API geändert.

![Octopress-Tweet](/img/2014-12-21-octopress.png)

Also habe ich mich einmal an den
[Hinweisen](http://octopress.org/docs/updating/) zum Aktualisieren von
Octopress orientiert. Hierzu werden die folgenden Schritte vorgeschlagen:

```
git pull octopress master      # Get the latest Octopress
bundle install                 # Keep gems updated
rake update_source             # update the template's source
rake update_style              # update the template's style
```

Soweit lief das auch. Es tauchten anschließend zwei Probleme auf:

1. Das `execjs` jammerte, dass ihm irgendwie eine
   JavaScript-Bibliothek fehlte. Nach kurzer Recherche gab es die
   Empfehlung, die Zeile `gem 'therubyracer' in das `Gemfile`
   aufzunehmen. Okay, das funktionierte schon einmal.

2. Bei den Feeds für die Kategorien jammerte das Octopress ein
   ungültiges Layout an. In `category_feed.xml` stand in der Tat
   `layout: nil`. Ich habe das auf `layout: page` geändert. Nun tat
   auch dies.

Mit dem Update funktioniert nun auch das Such-Formular wieder. 
