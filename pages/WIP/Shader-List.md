---
title: [ReShade Shader Directory]
type:
summary:
description: List of available shaders by category
sidebar: false
---
{% include callout.html type="note" content="This directory is not all encompassing.  Shaders not listed may be obsolete or have a newer free or equivalently priced version available." %}

{% include callout.html type="warning" content=" **This page is a work in progress and is currently incomplete.** " %}


**Other shader lists that are worth checking out:**
- **Framed Shaders Catalogue:** [https://framedsc.com/ReshadeGuides/shaderscatalogue.htm](https://framedsc.com/ReshadeGuides/shaderscatalogue.htm)
	- Doesnt't appear to have been updated in a while, so it doesn't include the latest shaders.
	- The website is also a very good source of information on how to take great looking screenshots.
- **PCGamingWiki ReShade page:** [https://www.pcgamingwiki.com/wiki/ReShade#List_of_known_shader_repositories/](https://www.pcgamingwiki.com/wiki/ReShade#List_of_known_shader_repositories/)
	- List of all the ReShade repositories that are available in the ReShade installer.  It doesn't list the individual shaders but it does have direct links to all the Github pages that the shaders are hosted on.
	- The PCGamingWiki ReShade page also lists games that ban or block ReShade and there's also a game compatibility list.


### Bloom shaders

{% capture bloom_table %}

| Shader            | Free or Paid | Developer                    | Link to Download or Patreon                                                                            | Notes                                                   |
| ----------------- | ----------------------- | ---------------------------- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------- |
| Convolution Bloom | Paid         | Marty McFly (Pascal Gilcher) | [https://www.patreon.com/c/mcflypg](https://www.patreon.com/c/mcflypg)                                 | Requires Immerse Ultimate / Path Tracers tier or higher |
| HDRBloom          | Free         | MaxG2D                       | [https://github.com/MaxG2D/ReshadeSimpleHDRShaders](https://github.com/MaxG2D/ReshadeSimpleHDRShaders) | Works in SDR or HDR                                     |
| Radon             | Paid         | Zenteon                      | [https://www.patreon.com/c/zenteon/](https://www.patreon.com/c/zenteon/)                               | Requires Renderer tier or higher                        |
| Solaris           | Paid         | Marty McFly (Pascal Gilcher) | [https://www.patreon.com/c/mcflypg](https://www.patreon.com/c/mcflypg)                                 | Requires Immerse Pro / Ray Tracers tier or higher       |
| Xenon             | Free         | Zenteon                      | [https://github.com/Zenteon/ZenteonFX](https://github.com/Zenteon/ZenteonFX)                           |                                                         |

{% endcapture %}

<div class="sortable-wrapper">
  {{ bloom_table | markdownify }}
</div>

### RT / GI Shaders

{% capture rt_table %}

| Shader  | Free or Paid | Developer                    | Link to Download or Patreon                                                                        | Notes                                             |
| ---------------- | ------------------- | ---------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| RTGI    | Paid         | Marty McFly (Pascal Gilcher) | [https://www.patreon.com/c/mcflypg](https://www.patreon.com/c/mcflypg)                             | Requires Immerse Pro / Ray Tracers tier or higher |
| TurboGI | Free         | Zenteon                      | [https://github.com/Zenteon/ZenteonFX](https://github.com/Zenteon/ZenteonFX)                       | Optional: can be used with Zenteon_Motion.fx      |
| UberRT  | Free         | AlucardDH                    | [https://github.com/AlucardDH/dh-reshade-shaders](https://github.com/AlucardDH/dh-reshade-shaders) |                                                   |
| ZenRT   | Paid         | Zenteon                      | [https://www.patreon.com/c/zenteon/](https://www.patreon.com/c/zenteon/)                           | Requires Renderer tier or higher                  |

{% endcapture %}

<div class="sortable-wrapper">
  {{ rt_table | markdownify }}
</div>


<style>

th {
  cursor: pointer;
  position: relative;
  padding-right: 24px;
  font-family: 'Segoe UI', sans-serif; /* or any other font you like */
}

th::after {
  content: "⇅";
  position: absolute;
  right: 6px;
  font-size: 1.2em; /* Bigger size */
  font-family: 'Segoe UI Symbol', 'Arial', sans-serif;
  color: #999;
}

th.sorted.asc::after {
  content: "↑";
  color: #111;
  font-size: 1.3em;
}

th.sorted.desc::after {
  content: "↓";
  color: #111;
  font-size: 1.3em;
}


 </style>

<script src="https://unpkg.com/tablesort@5.3.0/dist/tablesort.min.js"></script>
<script>
  document.addEventListener("DOMContentLoaded", function () {
    document.querySelectorAll(".sortable-wrapper table").forEach(function (table) {
      new Tablesort(table);

      table.querySelectorAll("th").forEach(function (th) {
        th.addEventListener("click", function () {
          table.querySelectorAll("th").forEach(function (header) {
            header.classList.remove("sorted", "asc", "desc");
          });

          setTimeout(function () {
            const sortOrder = th.getAttribute("aria-sort");
            th.classList.add("sorted");
            if (sortOrder === "ascending") {
              th.classList.add("asc");
            } else if (sortOrder === "descending") {
              th.classList.add("desc");
            }
          }, 10);
        });
      });
    });
  });
</script>







