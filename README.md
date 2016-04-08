# gravity-bubbles

> This component, using d3js API, draw animated bubbles chart with gravity

![Version](http://img.shields.io/version/0.9.5.png?color=green)


## Features
This is a visual component that draw a chart with centered gravity based on [d3](http://d3js.org/) API library.

Based on [Jim Vallandingham Blog Post](http://vallandingham.me/bubble_charts_in_d3.html), [Obama’s 2013 Budget Proposal](http://www.nytimes.com/interactive/2012/02/13/us/politics/2013-budget-proposal-graphic.html?_r=0) and [Automobile Force](http://projects.delimited.io/experiments/force-bubbles/radial.html), Gravity Bubbles it's a component that draw a collection of bubbles, and allow the user to compare data attributes by color and size. 

The main characteristic is the "gravity" to center, and hence its name. 

Also the component include 3 views:
* "all" view with unique center in center of chart
* "color" view, that are bubbles grouped by color fences, as vertical bands.
* A free group that is a name of property of data that can be used to group data, (such as country, category, contact id, etc).

###Some features
* Tooltip templated configuration
* Label templated configuration
* Animated transitions
* Size comparizons
* Group data capability
* Easy color schema changes
* Resizable data legend
* All items are visibles, including negatives and smallest data 

Examples
###Default:
![Gravity Bubbles ungruped](http://rawgit.com/lflores/gravity-bubbles/master/src/images/gravity-bubbles-default.png)
###Grouping by color:
![Gravity Bubbles Color groups](http://rawgit.com/lflores/gravity-bubbles/master/src/images/gravity-bubbles-group-color.png)
###Grouping by category:
![Gravity Bubbles Category groups](http://rawgit.com/lflores/gravity-bubbles/master/src/images/gravity-bubbles-group-category.png)
###Live Example
![Gravity Bubbles Example](http://www.triadsoft.com.ar/examples/gravity-bubbles/)
###Fiddle Example
![Gravity jsfiddle](http://jsfiddle.net/6cLpuL7j/8/)

###Colors Examples:
![Gravity Bubbles Blue Scheme](http://rawgit.com/lflores/gravity-bubbles/master/src/images/gravity-bubbles-blue.png)
![Gravity Bubbles Green Scheme](http://rawgit.com/lflores/gravity-bubbles/master/src/images/gravity-bubbles-green.png)
![Gravity Bubbles Brown Scheme](http://rawgit.com/lflores/gravity-bubbles/master/src/images/gravity-bubbles-brown.png)



## Get started
### Get started
If you want to see it in action, go to [jsfiddle](https://jsfiddle.net/leoflores/6cLpuL7j/6/) that explain some concepts of use, and show how to change some properties. Or if you want to see a more complex use, please go to [gravity-bubbles](http://www.triadsoft.com.ar/examples/gravity-bubbles.html)
Currently I'm documenting the project, and please, [contact me](mailto:flores.leonardo@gmail.com) if you want to help or discovered some issue.
To start using it, you must to download this proyect, and solve next dependencies.

Dependencies:
* [jquery](http://jquery.com/download/)
* [d3 api](https://github.com/mbostock/d3)
* [linear-gauge](https://github.com/lflores/linear-gauge) (only for examples)
* [jquery-ui](https://jqueryui.com/) (only for examples)



## Options
You can pass these options to the initialize function to set a custom look and feel for the plugin.

<table>
    <tr>
        <th>Property (Type)</th>
        <th>Default</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><strong>width</strong></td>
        <td>Calculated container width</td>
        <td>It's the external width of component. Doesn't include left and right margins</td>
    </tr>
  <tr>
        <td><strong>height</strong></td>
        <td>40</td>
        <td>It's the external height of component. Doesn't include top and bottom margins</td>
    </tr>
    <tr>
        <td><strong>points</strong></td>
        <td>[0, 25, 50, 75, 100]</td>
        <td>They are thresholds of color changes</td>
    </tr>
    <tr>
        <td><strong>colors</strong></td>
        <td>["#ff0000", "#ffa300", "#ffe100", "#fffa00", "#1f6f02"]</td>
        <td>They are the distinct colors that change on the thresholds</td>
    </tr>
     <tr>
        <td><strong>data</strong></td>
        <td></td>
        <td>This node is an object that receives parameter exclusive for data</td>
    </tr>
    <tr>
        <td><strong>data\label</strong></td>
        <td>none</td>
        <td>It has two optional parameter, they are template and formatter</td>
    </tr>
    <tr>
        <td><strong>data\tooltip</strong></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td><strong>data\sizeById</strong></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td><strong>data\colorById</strong></td>
        <td></td>
        <td></td>
    </tr>
</table>


## Callbacks
When the user click on bubble, a <strong>click</strong> is fired to comunicate that values have been clicked. It can be used to do a drilldown
<table>
    <tr>
        <th>Event</th>
        <th>Property</th>
        <th>Value</th>
    </tr>
    <tr>
        <td><strong>click</strong></td>
        <td>d</td>
        <td>Data Clicked</td>
    </tr>
</table>


## Plugin api
#### jQuery

```javascript
$(function() {
    // instantiate the plugin
    
    chart = new GravityBubbles({
                id: "vis",
               sizeById: "size",
                colorById: "perc",
                data: {
                    tooltip: function(d) {
                        //Parameter d is clicked data
                        //You can return a string template
                        return "<b>Name:</b>{name}<br><b>Size:</b> {size}<br><b>Size of Total:</b> {perc}%";
                    },
                    label: function (d) {
                        //Parameter d is clicked data
                        //You can return a string template
                        return "<b>Name:</b>{name}<br><b>Size:</b> {size}<br><b>Size of Total:</b> {perc}%";
                    },

                    onclick: function(d) {
                        //Parameter d is clicked data
                    }
                }
            });
});
```


## Browser Support
Native support

* Chrome
* Safari
* FireFox
* Opera
* Internet Explorer 9+

Support for Internet Explorer 9.


## Copyright
Copyright (c) 2016 Triad, contributors. Released under the MIT, GPL licenses