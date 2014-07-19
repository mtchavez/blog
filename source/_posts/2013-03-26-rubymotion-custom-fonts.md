---
layout: post
title: "Rubymotion Custom Fonts"
date: 2013-03-26 14:40
comments: true
#categories: ['rubymotion', 'ruby', 'iOS', 'UIFont', 'fonts']
---
In your Rakefile add your font in the app setup.

{%highlight ruby%}
Motion::Project::App.setup do |app|
  # App Settings
  app.fonts = ['st-marie.ttf']
end
{%endhighlight%}

Make sure your st-marie.ttf is in your resources directory


To use in your app do the following

{%highlight ruby%}
my_font = UIFont.fontWithName 'St Marie', size: 32
{%endhighlight%}

To find your font family name

{%highlight ruby%}
UIFont.familyNames.sort # Should contain 'St Marie'
{%endhighlight%}

To find the font names for a family name

{%highlight ruby%}
# Returns array of font names for 'St Marie'
UIFont.fontNamesForFamilyName 'St Marie'
{%endhighlight%}
