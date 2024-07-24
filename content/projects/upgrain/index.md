+++
title = 'Upgrain'
date = 2024-04-16T15:50:11-07:00
draft = false
summary = '''A habit adoption tracker that manages daily progress.'''
site = 'https://abstractionjackson.github.io/habit-tracker/'
githubRepo = 'habit-tracker'
technologies = ['postgres', 'flask', 'alpine', 'python']
[[resources]]
name = 'preview-image'
src = 'sunset.jpg'
+++

{{< figure src="/images/preview-habit-tracker.png" title="Landing Page, Web Application" class="preview" >}}

# Deep Habits
A simple CRUD app built on vanilla JS and SQLite.
## Usage
Open in the browser
## Features
- create habits by name
- view list of habits
- right-click to edit habit
  - edit text content, and click to update
- right-click to delete
## Justification
The Habit Tracker (...) is a stacic webpage that uses Web APIs and SQL.js to create and persist data.
The UI is reactive, thanks to vanilla browser events that rerender when data changes.
The stack is faily extensible, and the development process takes little time, especially considering GitHub co-pilot...
## Author
abstractionjackson
