---
title       : Carousel Layout
subtitle    : 
author      : Ramnath Vaidyanathan
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : solarized_light
widgets     : [bootstrap]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---

## Bootstrap Carousel

There are three things you need to do

1. Add `widget: bootstrap` in YAML front matter 
2. Ensure carousel template in `assets/layouts/carousel.html`
3. Markup carousel slide with `&carousel` to make use of layout.

---

## Carousel Slide

<a class='example'>slide</a>

    --- &carousel .span12
    
    ## Carousel
    
    
    *** {class: active, img: "http://placehold.it/960x500"}
    
    Image 1
    
    *** {img: "http://placehold.it/960x500"}
    
    Image 2



--- .RAW .smaller

<style>slide.smaller pre{font-size: 16px; line-height: 1.4em}</style>

<a class='example'>layout</a>

    ---
    layout: slide
    ---
    
    {{{ slide.content }}}
    <div id="{{slide.id}}-carousel" class="carousel slide {{slide.class}}">
      <!-- Indicators -->
      <ol class="carousel-indicators">
        {{# slide.blocks }}
        <li data-target="#{{slide.id}}-carousel" data-slide-to="{{num}}" class="{{class}}"></li>
        {{/ slide.blocks }}
      </ol>
      <!-- Wrapper for slides -->
      <div class="carousel-inner">
        {{# slide.blocks }}
        <div class="item {{class}}">
          <img src="{{img}}" alt="{{alt}}">
          <div class="carousel-caption">{{{ content }}}</div>
        </div>
        {{/ slide.blocks }}
      </div>
      <!-- Controls -->
      <a class="left carousel-control" href="#{{slide.id}}-carousel" data-slide="prev">&lsaquo;</a>
      <a class="right carousel-control" href="#{{slide.id}}-carousel" data-slide="next">&rsaquo;</a>
    </div>



--- &carousel .span12

## Carousel

<a class='example'>view</a>


*** {class: active, img: "http://placehold.it/960x500"}

Image 1

*** {img: "http://placehold.it/960x500"}

Image 2





