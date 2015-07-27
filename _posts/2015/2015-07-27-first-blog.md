---
layout: post
title: "Groovy 学习1"
date: 2015-07-27
tags: [groovy, time]
comments: true
share: false
---


{% highlight java %}
document=groovy.xml.DOMBuilder.parse(new FileReader('C:\\Users\\Administrator\\workspace\\FirstGroovyApp\\src\\language.xml'))

rootElement = document.documentElement

use(groovy.xml.dom.DOMCategory) {
	println "Languages and authors"
	languages = rootElement.language

	languages.each { language -> println "${language.'@name'} authored by ${language.author[0].text()}" }

	def languagesByAuthor = { authorName ->
		languages.findAll {it.author[0].text() ==authorName}.collect{ it.'@name'}.join(', ')
	}
	
	println "Language by Wirth:"+languagesByAuthor('Wirth')
}

{% endhighlight %}
