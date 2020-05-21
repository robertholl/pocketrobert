---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true
thumbnail: ""
sidebar: "left" # Enable sidebar (on the right side) per page
categories:
  - "Development"
tags:
  - "HTML"
menu:
    main:
      name: "{{ replace .Name "-" " " | title }}"
      weight: 10
---
