---
layout: post
title:      "A React Component Lifecycle Analogy"
date:       2018-02-26 18:23:39 -0500
permalink:  a_react_component_lifecycle_analogy
---

# Mounting

1. **componentWillMount** - executed right before mounting on DOM

* You're going to a concert but in order to enter, you must get your ticket checked. If somehting is wrong with you're ticket, you will get and "error" and be redirected elsewhere.

2. **componentDidMount** - called when component is initialized, used to connect to API

* Everyone is "rendered" into their seats, the lights are on and stage is set up. We need to "call" the band to come on stage. 


# Updating

3. **componentWillReceiveProps** - use new props to update component's state

* The band comes on stage, therefore the lights turn off.

4. **shouldComponentUpdate** -  compare old and new props to decide on a re-render

* The band is still playing, nothing has changed. No need to clear the stage or turn the lights on.

5. **componentWillUpdate** - props change and should component update becomes true, connect to API

*  Lights come back on and we can add a performance to the band's repertoire.
 
 # Unmounting
 
6. **componentWillUnmount** - clear out anything that happened during componentDidMount

 * The band can be removed from the stage.

 
 
