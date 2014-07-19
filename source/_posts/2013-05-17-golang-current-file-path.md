---
layout: post
title: "Golang Current File Path"
date: 2013-05-17 14:40
comments: true
#categories: ['Go', 'Golang', 'filepath']
---

I recently needed to get the current file absolute path from a go file.
You first need to get the runtime package which is a part of Go

{%highlight go%}
import "runtime"
{%endhighlight%}

Next you can use the ```Caller``` method and capture the filename. We need to
give this function a ```1``` to tell it to skip up a caller. You can read more
about the function [here](http://golang.org/pkg/runtime/#Caller)

{%highlight go%}
_, filename, _, ok := runtime.Caller(1)
{%endhighlight%}

The filename will be the path up to the current directory of the file that
calls this function. The ```ok``` is to check if the function call was able to
find the information requested.

So in practice if you wanted to get a config file up a directory and in a
config directory you could do the following

{%highlight go%}
filepath := path.Join(path.Dir(filename), "../config/settings.toml")
{%endhighlight%}
