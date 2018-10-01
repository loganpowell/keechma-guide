---
title: Keechma Guide
separator: <!--s-->
verticalSeparator: <!--v-->
theme: white
revealOptions:
    transition: 'slide'
    progress: true
    touch: true
    history: true
    slideNumber: true
---

<!--

,d88~~\ 888 ,e,       888                 ,d88~~\   d8           888                  
8888    888  "   e88~\888  e88~~8e        8888    _d88__ Y88b  / 888  e88~~8e   d88~\ 
`Y88b   888 888 d888  888 d888  88b       `Y88b    888    Y888/  888 d888  88b C888   
 `Y88b, 888 888 8888  888 8888__888        `Y88b,  888     Y8/   888 8888__888  Y88b  
   8888 888 888 Y888  888 Y888    ,          8888  888      Y    888 Y888    ,   888D 
\__88P' 888 888  "88_/888  "88___/        \__88P'  "88_/   /     888  "88___/  \_88P  
                                                         _/                            
-->

<style>
.reveal p {
 font-size: 0.7em;
}
.reveal section img { 
  background:none; 
  border:none; 
  box-shadow:none; 
}
.reveal img
{
  border: none;
  box-shadow: none;
  max-height: calc(66vh);
  text-align: left; 
}
.reveal table {
  margin: auto;
  border-collapse: collapse;
  border-spacing: 0;
}

.reveal table th {
  font-weight: bold;
}

.reveal table th,
.reveal table td {
  text-align: left;
  padding: 0.2em 0.5em 0.2em 0.5em;
  border-bottom: 1px solid;
  font-size: 0.7em;
}

</style>


<!--
                    d8   888 ,e,                    
 e88~-_  888  888 _d88__ 888  "  888-~88e  e88~~8e  
d888   i 888  888  888   888 888 888  888 d888  88b 
8888   | 888  888  888   888 888 888  888 8888__888 
Y888   ' 888  888  888   888 888 888  888 Y888    , 
 "88_-~  "88_-888  "88_/ 888 888 888  888  "88___/  
                                                    
                                                  

- Keechma Overview
  - A State Management Framework for Reagent (batteries included)
  - Reagent is a ClojureScript wrapper around React.js
  - React.js is a "virtual DOM" rendering library
- TLDR;
  - React is great at efficient rendering only the parts of your UI that need updating
  - React is NOT great for medium to large sized applications by itself. It is purely a rendering library
  - There are a slew of additional libraries you'll need for a production-ready React app and you might have become a bit disenchanted by the complexity - and somewhat disoriented nature - of the Ecosystem
  - Even after finding a React state management library you like, you begin asking yourself: "But, how do I manage side effects?" and/or "how do I make this work with a router?"
    - Redux vs Mobx vs Apollo Link State
    - Redux Saga vs Logic vs Thunk vs Mobx State-Tree
    - React Router vs Reach Router vs Mobx Router vs Mobx React-Router
    - etc...
    - There's an entire cottage industry spun off of the React library and there be dragons
  - Keechma answers all of these questions in a turn-key solution, elegantly
- Prerequisites (There are no free lunches)
  - Would you rather spend your time learning a library that could go out of fashion or edifying yourself as a better programmer? If the former, you may be in the wrong place.
  - Clojure/Script (moderate) :: let this be your gateway drug to a practical yet functional programming language
  - React.js (basic)
  - Reagent (moderate)
  - We will cover this briefly herein, but we'll refer to some excellent external resources at the end of this guide to get you on the expedited learning path.
- React.js Overview
  - Functional Inclinations
    - Pure functions are preferred over Classes
    - Immutable data structures allow for "shallow" comparison-based DOM re-rendering, improving performance
    - ClojureScript + React = 💖
  - React Syntax
    - How React compiles to JavaScript
  - React state management options
    - Redux (most popular)
      - incorporates the "flux" pattern of uni-directional data flow
      - immutable state container
    - MobX (Reactive/Rx)
      - graph-like state management
      - state containers are mutable
    - Apollo Link State
      - Relay (another library from the Facebook team) inspired graph-based state management
      - state is derived from GraphQL queries and normalized for deduplication
  - React router options
    - React Router
    - Reach Router
    - Redux First Router
    - Curi
  - React "middleware" options (for side effects)
    - Redux Thunk
    - Redux Saga
    - Redux Logic
- Reagent Overview 
  - Wraps React.js to avail components via Clojure data structures
  - Three varieties of components (forms): 
    - pure functions (no local state)
    - 
- Clojure/Script Tutorials and Resources
  - [Clojure on Exercism](https://exercism.io/my/tracks/clojure)
  - [Recommended Reading: SICP](http://web.mit.edu/alexmv/6.037/sicp.pdf)
    - [Good Reads: 4.44 stars, 3,662 Ratings at time of post](https://www.goodreads.com/book/show/43713.Structure_and_Interpretation_of_Computer_Programs)
  - [Living Clojure](https://www.goodreads.com/book/show/24701168-living-clojure)
- Reagent Tutorials and Resources
  - [PurelyFunctional.tv Overview](https://purelyfunctional.tv/guide/reagent/)
  - [Jacek Schae Video Tutorials](https://www.jacekschae.com/courses/)
  - [Timothy Pratley Deep Dive Articles](http://timothypratley.blogspot.com/2017/01/reagent-deep-dive-part-1.html)
  - [Reagent Docs](http://reagent-project.github.io/docs/master/index.html)
  

- React Ecosystem Decision Tree of Doom
  - ![Super Quantified Chart](https://docs.google.com/drawings/d/e/2PACX-1vTfmUeJgxFHvfLDH_JocbC_uPn6CckPhCb9COrzfmW_-CS0gk4jKQnHH1IZUAkJa1QKvBzSy8eoo7Ea/pub?w=575&h=479)

-->  






















<!--

888            d8                   
888 888-~88e _d88__ 888-~\  e88~-_  
888 888  888  888   888    d888   i 
888 888  888  888   888    8888   | 
888 888  888  888   888    Y888   ' 
888 888  888  "88_/ 888     "88_-~  
                                    
-->                                  



![Keechma logo](https://keechma.com/keechma-reagent-clojurescript-logo.png)

### Keechma Microframework Guide

Note: This is how we include speaker notes if so desired

<!--v-->

## Introduction

Keechma is a micro-framework for creating web applications in ClojureScript

- Deterministic application behavior
- Integrated router (not an awkward appendage)
- Flux-inspired uni-directional data flow
- Battle-tested (yeah, I said it)

...[and more](https://github.com/keechma/keechma)

<!--

888~-_                                 d8   
888   \   e88~~8e    /~~~8e   e88~~\ _d88__ 
888    | d888  88b       88b d888     888   
888   /  8888__888  e88~-888 8888     888   
888_-~   Y888    , C888  888 Y888     888   
888 ~-_   "88___/   "88_-888  "88__/  "88_/ 
                                                                                     
-->






<!--s-->

## React Overview

[React](https://reactjs.org/) is a JavaScript ["virtual DOM"](https://reactjs.org/docs/faq-internals.html) rendering library, which [fosters a preference](https://reactjs.org/docs/optimizing-performance.html) for the use of functional programming, immutable data structures and uni-directional data flow (aka: ["flux"](https://github.com/facebook/flux/tree/master/examples/flux-concepts)) in web applications


![React Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/2000px-React-icon.svg.png)

<!--s-->

# We all love React, until we don't

<!--v-->

![Super Quantified Chart](https://docs.google.com/drawings/d/e/2PACX-1vTfmUeJgxFHvfLDH_JocbC_uPn6CckPhCb9COrzfmW_-CS0gk4jKQnHH1IZUAkJa1QKvBzSy8eoo7Ea/pub?w=862&h=718)

<!--s-->

## React + ClojureScript = 💖

What other language fosters functional programming and immutable data structures? 

> Clojure(Script) is built around [these principles](https://clojure.org/about/functional_programming)

For an opinion piece on the comparison of writing functional programs in JavaScript vs ClojureScript, check out [this Hackernoon article](https://hackernoon.com/functional-programming-in-javascript-is-an-antipattern-58526819f21e)


<!--

888~-_                             /                      d8   
888   \   e88~~8e    /~~~8e  e88~88e  e88~~8e  888-~88e _d88__ 
888    | d888  88b       88b 888 888 d888  88b 888  888  888   
888   /  8888__888  e88~-888 "88_88" 8888__888 888  888  888   
888_-~   Y888    , C888  888  /      Y888    , 888  888  888   
888 ~-_   "88___/   "88_-888 Cb       "88___/  888  888  "88_/ 
                              Y8""8D                           
-->
  
<!--v-->

## Reagent Basics

![React + ClojureScript](https://practicalli.github.io/clojurescript/images/clojurescript-react.png)

Keechma is a state management, delegation and routing framework built on top of the ClojureScript [Reagent](https://reagent-project.github.io/) library, which is a wrapper around the popular React JavaScript view rendering/virtual DOM library.
 
<!--v-->

## Syntax Comparisons

## React 
```js
function Welcome({name}) {return <h1>Hello, {name}</h1>}
```

## Reagent 
```clojure
(defn Welcome [name] [:h1 "Hello, " name])
```
                                
<!--v-->

However, there be dragons here too...

<!--v-->

![Reagent Ecosystem](https://docs.google.com/drawings/d/e/2PACX-1vS_F7uKIluF_DLfR6LxrDkFkOjnBtgFYrX2X2xFd6NrEBzkPPzIYVy_spLpHeCT7Slk2hh8httF3MSG/pub?w=862&h=718)


<!--s-->



<!--

888  /                               888                              
888 /     e88~~8e   e88~~8e   e88~~\ 888-~88e 888-~88e-~88e   /~~~8e  
888/\    d888  88b d888  88b d888    888  888 888  888  888       88b 
888  \   8888__888 8888__888 8888    888  888 888  888  888  e88~-888 
888   \  Y888    , Y888    , Y888    888  888 888  888  888 C888  888 
888    \  "88___/   "88___/   "88__/ 888  888 888  888  888  "88_-888 
                                                                                  
-->


# Keechma Overview

Watch a [video overview](https://www.youtube.com/watch?v=2BF6yKIpXmM) from the [author of Keechma](https://twitter.com/mihaelkonjevic)

<iframe width="700" height="400" src="https://www.youtube.com/embed/2BF6yKIpXmM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

<!--v-->

![Route-Driven Rendering Cycle](https://docs.google.com/drawings/d/e/2PACX-1vSKp5waBcVL7aostQE641TXAcexUp3FT3IMEio7LE8Cwf1Z_G92U4z6g_21hIQhmBU_EkPUj2OOiT6D/pub?w=1441&h=934)

<!--v-->

![UI-Driven Rendering Cycle](https://docs.google.com/drawings/d/e/2PACX-1vR4lnMDuNOEHOws3naksreVIYpp3-TEzTmyL-8xivSiNDgAfhMIkDxObTJKr75-IfvoE8i85cKFe4tZ/pub?w=1441&h=934)
        
        
<!--v-->

Layer                                                                             | Function
---                                                                               | ---
[Router](https://keechma.com/guides/router/)                                      | URL <=> Signal Data Translation
[Controller Manager](https://keechma.com/api/keechma/keechma_controller-manager/) | Receives the Signal Data and starts/stops controllers
[Controllers](https://keechma.com/guides/controllers/)                            | Change the application state and encapsulate async code with/out side effects 
[Entity DB](https://keechma.com/guides/entitydb/)                                 | Application state container 
[UI](https://keechma.com/guides/ui-system/)                                       | Propagates state changes to the view and communicates with Router/Controller Manager 

<!--v-->

### Through a Different Looking Glass

These layers can also be seen as functions wrapping other functions:

![Supersets Graph](https://docs.google.com/drawings/d/e/2PACX-1vSqEsWI2qt1FjX2Dl954D29DnsyRxyFcx3xZkgc4QZZNmLF1JkRcGHWp8hEHy5xOeaeLdnvHCUxTry7/pub?w=465&h=536)
 

<!--v-->

## Route-driven Rendering

```clojure
(-> url
    (extract-route-data)
    (invoke-controller-manager)
    (update-app-db)
    (render-ui))
```

<!--v-->

## UI Command-driven Rendering

```clojure
(-> command
    (invoke-controller-manager)
    (update-app-db)
    (render-ui))
```

<!--v-->



<!--

888~-_   ,e,       /                    d8   
888   \   "  e88~88e  e88~~8e   d88~\ _d88__ 
888    | 888 888 888 d888  88b C888    888   
888    | 888 "88_88" 8888__888  Y88b   888   
888   /  888  /      Y888    ,   888D  888   
888_-~   888 Cb       "88___/  \_88P   "88_/ 
              Y8""8D                         
                     
-->



## Let's Take it from the Top



<!--
                           d8                    
888-~\  e88~-_  888  888 _d88__  e88~~8e  888-~\ 
888    d888   i 888  888  888   d888  88b 888    
888    8888   | 888  888  888   8888__888 888    
888    Y888   ' 888  888  888   Y888    , 888    
888     "88_-~  "88_-888  "88_/  "88___/  888    
                                                                  
-->



<!--s-->

## [`router`](https://keechma.com/api/router/)


<!--v-->

## Example  

```clojure
(def routes [":page"
             ":page/:note-id"])
```


<!--v-->

## Valid Routes

URL                                              | Ex.
---                                              | ---
`/starred`                                       | 
`/starred/:id`                                   | `1`
`/starred?limit=10`                              |   
`/starred?offset=20`                             |   
`/starred?limit=10&offset=20`                    |            
`/starred/this-is-the-note-id?limit=10`          |                      
`/starred/this-is-the-note-id?offset=20`         |                       
`/starred/this-is-the-note-id?limit=10&offset=20`|                                

<!--v-->

### Controller Manager Reacts to Route Change

```
https://example.com/starred
```

Prev Value | New Value | Stop  | Start | Final State
---------- | --------- | :---: | :---: | ---
`nil`      | "list"    |       | ✔️    | `start`

```
https://example.com/starred/1
```

Prev Value | New Value | Stop  | Start | Final State
---------- | --------- | :---: | :---: | ---
`nil`      | "details" |       | ✔️    | `start`
"list"     | "list"    |       |       | `start`

<!--v-->


### Visualization

![Controller Manager](https://keechma.com/controller_manager.svg)

<!--v-->

There are two ways to affect the application state:

1. URL change
2. UI action (e.g. clicking on a button) which sends the command to the controller

<!--v-->

![Router Driven State Changes](https://keechma.com/route_change.svg)

<!--v-->

![UI Driven State Changes](https://keechma.com/command_sent.svg)


<!--s-->

## [`controller-manager`](https://keechma.com/api/keechma/keechma_controller-manager/)

<!--

                                                 /                  
888-~88e-~88e   /~~~8e  888-~88e   /~~~8e  e88~88e  e88~~8e  888-~\ 
888  888  888       88b 888  888       88b 888 888 d888  88b 888    
888  888  888  e88~-888 888  888  e88~-888 "88_88" 8888__888 888    
888  888  888 C888  888 888  888 C888  888  /      Y888    , 888    
888  888  888  "88_-888 888  888  "88_-888 Cb       "88___/  888    
                                            Y8""8D                                    
                     
-->

<!--v-->



<!--

                            d8                   888 888                  
 e88~~\  e88~-_  888-~88e _d88__ 888-~\  e88~-_  888 888  e88~~8e  888-~\ 
d888    d888   i 888  888  888   888    d888   i 888 888 d888  88b 888    
8888    8888   | 888  888  888   888    8888   | 888 888 8888__888 888    
Y888    Y888   ' 888  888  888   888    Y888   ' 888 888 Y888    , 888    
 "88__/  "88_-~  888  888  "88_/ 888     "88_-~  888 888  "88___/  888    
                                                                                             
                     
-->



<!--s-->

## [`controller`](https://keechma.com/api/keechma/keechma_controller/)

<!--v-->

## Pipeline!


<!--v-->

## Inspired by:

["Railway Oriented Programming" - Scott Wlaschin](https://fsharpforfunandprofit.com/posts/recipe-part2/)

<!--v-->


<!--
                                            d8               d8             
  /~~~8e  888-~88e  888-~88e        d88~\ _d88__   /~~~8e  _d88__  e88~~8e  
      88b 888  888b 888  888b ____ C888    888         88b  888   d888  88b 
 e88~-888 888  8888 888  8888       Y88b   888    e88~-888  888   8888__888 
C888  888 888  888P 888  888P        888D  888   C888  888  888   Y888    , 
 "88_-888 888-_88"  888-_88"       \_88P   "88_/  "88_-888  "88_/  "88___/  
          888       888                                                     
                            
-->





<!--s-->

## [`app-state`](https://keechma.com/api/keechma/keechma_app-state/)




<!--

888   | 888 
888   | 888 
888   | 888 
888   | 888 
Y88   | 888 
 "8__/  888 
              
                                                  
-->


<!--s-->

## [`ui-component`](https://keechma.com/api/keechma/keechma_ui-component/)


<!--v-->

# ARCHIVE

<!--v-->

### Architecture

![Architectural Graph](https://docs.google.com/drawings/d/e/2PACX-1vTWjOU7M5psI-ylgPRwEHxLkM3klj-oyPVRQlTb81_W4laTP3bzBijqHZrvaMoxRg5vxm37vLh2fRdS/pub?w=695&h=479)

<!--v-->

## URL/Route-driven, State Derived UI Rendering

Cause                               | Effect ➲ 
---                                 | ---
URL change                          | Router converts URL ➲ `{...data...}`
Data sent to controller manager     | ➲ Start or stop the relevant controllers
According controllers stop/start    | ➲ Application state changed
Application state changed           | ➲ Relevant UI components rendered

<!--v-->

## UI-driven, State Derived UI Rendering

Cause                               | Effect ➲  
---                                 | ---
User performs action (e.g. click)   | Command ➲ Controller Manager
Command to Controller Manager       | `:topic` ➲ Start/stop controllers 
According controllers stop/start    | ➲ Application state changed
Application state changed           | ➲ Relevant UI components rendered

<!--v-->