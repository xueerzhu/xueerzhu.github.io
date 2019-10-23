---
layout: post
title:  "Teach a gameplay mechanics through storytelling"
date:   2013-12-23 00:18:23 +0700
categories: [design]
---
My professor likes to think that Middle-earth: Shadow of Mordor is a systemically speaking flawed game. Its nemesis system innovation revolves around AI and NPC behavior. Admittedly, part of its gameplay were repetitive and tedious. This system has a special place in my heart due to how much of an impact it has in making I feel like my influence in the game was scaled linearly through progression. 

It had my heart with the intro cutscene/tutorial part of the game, especially when it's trying to teach me the sneaking mechanics. 
![how to sneak](/assets/sneaking-tutorial.jpeg)





Parsing JSON with Ruby is actually extremely easy. All you have to do is have the json gem installed (`gem install json`) and call the `JSON.parse` method on the JSON data to convert it to ruby hashes. If you look at this small program here, you can see how I have implemented parsing JSON in Ruby.

{% highlight ruby %}
#!/usr/bin/env ruby

require 'json'
require 'net/http'
require 'libnotify'

def parsejson
    file = "http://api.openweathermap.org/data/2.5/find?q=London&mode=json"
    response = Net::HTTP.get_response(URI.parse(file))
    weatherjson = response.body
    actual = JSON.parse(weatherjson)

    # check for errors
    if actual.has_key? 'Error'
        raise "error with the url"
    end

    results = []

    actual["list"].each do |listitem|
        weather = listitem["weather"]
        weather.each do |weath|
            results.push(weath["description"])
        end
        main = listitem["main"]
        temp = main["temp"] - 273.15
        results.push ("%.2f" % temp)
    end

    return results
end
{% endhighlight %}
