---
layout: post
title: "Groovy解析xml文件"
date: 2015-07-27
tags: [groovy, time]
comments: true
share: false
---

###第一种方式:使用DomCategory    
{% highlight groovy %}
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

###第二种方式：使用XmlParser    
{% highlight groovy %}
languages=new XmlParser().parse('C:\\Users\\Administrator\\workspace\\FirstGroovyApp\\src\\language.xml')

println "Languages and authors"

languages.each { println "${it.@name} authored by ${it.author[0].text()}" }

def languagesByAuthor={ authorName->
	languages.findAll {it.author[0].text()==authorName}.collect{ it.@name }.join(', ')
}

println "Languages by Wirth: " +languagesByAuthor('Wirth')
{% endhighlight %}

###第三种方式:使用XmlSlurper    
{% highlight groovy %}
languages = new XmlSlurper().parse('C:\\Users\\Administrator\\workspace\\FirstGroovyApp\\src\\language.xml')
println "Languages and authors"

languages.language.each { println "${it.@name} authored by ${it.author[0].text()}" }

def languagesByAuthor = { authorName ->
	languages.language.findAll {
		it.author[0].text()==authorName
	}.collect{it.@name}.join(', ')
}

println "Languages by Wirth:"+languagesByAuthor('Wirth')
{% endhighlight %}

####例子xml文件    
