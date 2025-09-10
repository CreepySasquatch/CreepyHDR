---
title: [HDR Guide Template]
type: Template
summary: HDR Guide Template
description: HDR Guide Template
sidebar: false
---
{% include callout.html type="note" content="Put your note here." %}
- Other callout types: tip, important, warning

## First Topic

> Content

## Second Topic

**Collapsible text**

  <details>
  <summary>Click to expand:</summary>
	<ol>
	Text goes here
	</ol>
	</details>
<br>
Is made with this code snippet:
	
```
<details>
<summary>Click to expand:</summary>
<ol>
Text goes here
</ol>
</details>
```

**Collapsible text with bulleted list**

  <details>
  <summary>Click to expand:</summary>
	<ol>
	<ul>
    <li>Item 1</li>

    <li>Item 2 with link: <a href="https://github.com/CreepySasquatch">Creepy's GitHub Page</a></li>

    <li><strong>Item 3 Bolded</strong></li>
	</ul>
	</ol>
	</details>
<br>
Is made with this code snippet:

```
<details>
<summary>Click to expand:</summary>
<ol>
<ul>
<li>Item 1</li>

<li>Item 2 with Link: <a href="https://github.com/CreepySasquatch">Creepy's GitHub Page</a></li>

<li><strong>Item 3 Bolded</strong></li>
</ul>
</ol>
</details>
```	

## To insert image:

{% include image.html file="/infrastructures/ELIXIR-logo.svg" caption="Figure 1. Say something about this pic." alt="ELIXIR logo" max-width="10" %}

## To get images loaded correction in the ICAT embed, make sure the full image URL is listed inside of the HTML file.
- If image is stored on github, right click on the image and open in a new window to get the accurate address.  
- Each image in the comparison will be have it's link posted twice.
- Example: https://github.com/CreepySasquatch/CreepyHDR/blob/main/assets/ICAT_Comparisons/ACShadows-Image-1.png?raw=true

<!-- Insert comment here that you don't want to appear on the website -->

