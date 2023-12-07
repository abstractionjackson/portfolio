+++
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
subtitle = ''
summary = ""
date = {{ .Date }}
draft = true
github_repo = "https://github.com/{{ site.Params.github }}/{{ .Name }}"
[[resources]]
name = 'preview'
src = 'images/preview.*'
+++
