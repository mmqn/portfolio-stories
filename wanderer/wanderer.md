# Wanderer

<p align="center"><img title="Wanderer Logo" alt="Wanderer Logo" src="https://raw.githubusercontent.com/mmqn/portfolio_stories/master/wanderer/resources/wanderer_logo.png" width="100px" style="border:none;box-shadow:none;"></p>

<p align="center"><a href="https://mmqn.github.io/wanderer">Live App Preview</a></p>

I should preface this project by saying it in no way is intended to be a widely used app. It's simply a personal project to solve a personal need at the time. It gave me the chance to learn more about React outside of my job and be free of the visual design contraints of an established system.

![Map View](https://raw.githubusercontent.com/mmqn/portfolio_stories/master/wanderer/resources/cover.png "Map View")

## The need

I've been to a lot of places, and it can be overwhelming to organize them all. I'm aware of apps out there that allow you to log places, both built into ubiquitous apps—like Apple Maps or Google Maps—but after trying many of them, I've found that they are either too sparse in the features I want or too bloated with clutter. Also, I didn't want my extensive library of places to be tied to a single platform with no way to ever migrate it (like exporting as JSON/Excel).

## The solution

So I decided to build my own web app that'll allow me to track all the places I've been to and allow me to organize it the way I want to. In the end, it can essentially be summarized as a high-level note-taking app with a map. You can read more about the specifications of the app [here](https://github.com/mmqn/wanderer), or directly view the live app [here](https://mmqn.github.io/wanderer).

In addition to being able to experiment with some design and UI ideas, this app also gave me complete control over my data, so I'm free to experiment with it however I wanted to.

## The UI

<video title="List View" autoplay playsinline loop muted style="margin-top:18px;"><source src="https://raw.githubusercontent.com/mmqn/portfolio_stories/master/wanderer/resources/list_view.mp4" type="video/mp4"></video>

The color for me is usually what drives the way a user interface usually ends up looking. For this project, I felt like the appropriate color combination would be gold (<code style="background-color:#e4c200;color:white;">#e4c200</code>) and dark gray (<code style="background-color:#1e1e1e;color:white;">#1e1e1e</code>). That, paired with a italicized monospace typeface (Space Mono) and sans serif typeface (Karla), gives the app a somewhat upscale look and feel while still being grounded as a practical and technical service.

Every transition in the UI should be smooth and gradual. They all have the same timing function: `cubic-bezier(0.2, 0.8, 0.6, 1)`. This transition starts out fast but eases in to its final state; hovering over a card activates a pleasing and soothing glow of gold.

<video title="Expanding Cards" autoplay playsinline loop muted><source src="https://raw.githubusercontent.com/mmqn/portfolio_stories/master/wanderer/resources/expanding_card.mp4" type="video/mp4"></video>

## Everything is a filterable data point

<video title="Data-Point Filtering" autoplay playsinline loop muted style="margin-top:18px;"><source src="https://raw.githubusercontent.com/mmqn/portfolio_stories/master/wanderer/resources/data_point_filtering.mp4" type="video/mp4"></video>

One of the core principles for this app is the idea that every data point in a data-driven app should be an actionable element that can retrieve similar data.

(I actually developed this idea in a [prior project](https://github.com/mmqn/xe_dataset).)

For example, say you're looking at the unfiltered list of places: restaurants and coffee shops intertwined with museums. You see a Mediterranean restaurant and realize that that's what you're craving. You can simply click on the "Mediterranean" tag in the card and the entire list will automatically filter down to just Mediterranean restaurants.

So now you know you definitely want Mediterranean, but there's still a lot of places to choose from. You're not in the mood to drive far and only want to see places in Los Angeles. Well you can just click on the "Los Angeles" city name of the address in the card you were looking at and now your list is filtered a second time, down to just Mediterranean places in Los Angeles.

So yes, you can more directly activate these two filters using the search bar to look up "Mediterranean" and "Los Angeles". However, this system of making every data point an actionable filter allows the user to follow their whimsical train of thoughts with less effort.

When the user sees something of interest, they can immediately click on it where their mouse already is, as opposed to having to moving up to a search bar, process what to type, and typing it. Those couple of saved seconds saves some mental energy, and doesn't break the user's train of thought or impetus.

## Omni-search

<video title="Search Filtering" autoplay playsinline loop muted style="margin-top:18px;"><source src="https://raw.githubusercontent.com/mmqn/portfolio_stories/master/wanderer/resources/omni_search_filtering.mp4" type="video/mp4"></video>

This feature kind of goes hand-in-hand with the one above: because every data point is an actionable element already capable of being applied to the filtering routine, I just needed to aggregate those data points into a single list of unique values.

As a result, the search bar returns a series of type-value pairs. For example:

- `{ type: "Category", value: "Coffee" }`
- `{ type: "City", value: "Pasadena" }`
- `{ type: "Name", value: "Pasta Sisters" }`

Each type-value pair performs the same filtering routine as when the user clicks on a data point in a card.
