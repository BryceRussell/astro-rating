# Astro Rating :star: :star: :star: :star: :star:

Astro component that uses stars to display the rating of a product, post, comment, etc.

Uses [tailwindcss](https://tailwindcss.com) for custom class based styling and [astro-icon](https://github.com/natemoo-re/astro-icon) to customize the star icons

## How to use

__Install package__:

```npm i astro-rating```

__Inside a .astro component/layout/page__:

![Single Default Rating](https://raw.githubusercontent.com/BryceRussell/astro-rating/main/examples/single.PNG)

```
import { Rating } from 'astro-rating';

//Create a rating
<Rating total="90876" rate="2.5" max="5" />
```

## Examples

### Default

![Rating Component Example](https://raw.githubusercontent.com/BryceRussell/astro-rating/main/examples/default.PNG)

```
<Rating total="1279643" rate="5" max="5" />
<Rating total="673923" rate="4.5" max="5" />
<Rating total="90876" rate="3.5" max="5" />
<Rating total="8634" rate="3" max="5" />
<Rating total="178" rate="2.5" max="5" />
<Rating total="39" rate="1.5" max="5" />
<Rating total="8" rate="0.5" max="5" />
<Rating total="0" rate="0" max="5" />
```

### Astro-Icon Support

astro-rating uses [astro-icon](https://github.com/natemoo-re/astro-icon#readme) to deliver svgs for displaying stars. If you want to use different star icons [read about](https://github.com/natemoo-re/astro-icon#icon-packs) the Icon name property and how it uses [Iconify](https://iconify.design) to fetch any popular icon from a bunch of the most popular icon packs.

#### Phosphor

![Phosphor](https://raw.githubusercontent.com/BryceRussell/astro-rating/main/examples/phosphor.PNG)

```
const phosphor = {
  rate: "8.5",
  max: "10",
  total: "32769",
  full: "ph:star-fill",
  half: "ph:star-half-fill",
  empty: "ph:star",
  starClass: "text-yellow-500 w-4 h-4"
}

<Rating {...phosphor}/>
```

#### Material Design Icons

![Material Design](https://raw.githubusercontent.com/BryceRussell/astro-rating/main/examples/material-design.PNG)

```
const material_design = {
  rate: "2.5",
  max: "5",
  total: "72",
  full: "mdi:star",
  half: "mdi:star-half-full",
  empty: "mdi:star-outline",
  starClass: "text-yellow-500 w-4 h-4"
}

<Rating {...material_design}/>
```

### Custom Styling

Use [tailwindcss](https://tailwindcss.com) and the provided class props to customize the look of your rating

![Reversed Column](https://raw.githubusercontent.com/BryceRussell/astro-rating/main/examples/col-reversed.PNG)

```
const col-reverse = {
  rate="9.5" 
  max="10"
  total="872"
  class: "flex flex-col-reverse items-end",
}

<Rating {...col-reverse}/>
```

![Reversed Row](https://raw.githubusercontent.com/BryceRussell/astro-rating/main/examples/row-reversed.PNG)

```
const row-reverse = {
  rate="2.5" 
  max="5"
  total="178"
  class: "flex flex-row-reverse items-center gap-1",
}

<Rating {...row-reverse}/>
```

## Props

Propname | Type | Description | Default
------------ | ------------- | ------------- | -------------
rate|number\|string|0|# between 0 and max
max|number\|string|5|max number of stars|5
total|number\|string||total # of ratings
full|string|star-full|[astro-icon](https://github.com/natemoo-re/astro-icon#readme) Icon name prop representing a full star
half|string|star-half|[astro-icon](https://github.com/natemoo-re/astro-icon#readme) Icon name prop representing a half star
empty|string|star-empty|[astro-icon](https://github.com/natemoo-re/astro-icon#readme) Icon name prop representing a empty star
totalClass|string|leading-none text-xs text-gray-300|class of the total ratings span element
starsClass|string|flex items-center|class to div that holds all stars
starClass|string|h-4 w-4|class to div that surrounds the icons svg element
...attrs|string|```{class:"flex items-center gap-1"}```|apply any html attribute like 'class', 'id', or 'style' to the rating container

## Advanced Rating

If you need more control over your Rating component use a ARating component. ARating allows you to add attributes to any element inside your rating using an object.

### Examples

ARating uses all the same props but puts them inside of any object so you can defined any attribute you would like for that element:

![ARating](https://raw.githubusercontent.com/BryceRussell/astro-rating/main/examples/advanced.PNG)

```
import { ARating } from 'astro-rating';

const my_rating = {
  max: 5,
  rate: 2.5,
  full: "mdi:star",
  half: "mdi:star-half-full",
  empty: "mdi:star-outline",
  total: {
    text: "9876",
    class: "leading-none text-xs text-gray-300",
  },
  stars: {
    class: "flex items-center"
  },
  star: {
    class: "h-4 w-4 text-yellow-300"
  },
  id: "my-rating"
}

<ARating {...my_rating}/>
```

Propname | Type | Description | Default
------------ | ------------- | ------------- | -------------
rate|number\|string|0|# between 0 and max
max|number\|string|5|max number of stars|5
full|string|star-full|[astro-icon](https://github.com/natemoo-re/astro-icon#readme) Icon name prop representing a full star
half|string|star-half|[astro-icon](https://github.com/natemoo-re/astro-icon#readme) Icon name prop representing a half star
empty|string|star-empty|[astro-icon](https://github.com/natemoo-re/astro-icon#readme) Icon name prop representing a empty star
total|object|```{class:"leading-none text-xs text-gray-300"}```|Total ratings span element
total.text|string\|number||Total rating span text
stars|object|```{full: "star-full",half: "star-half",empty: "star-empty",class: "flex items-center"}```|Div with all star svgs
star|object|```{class:"flex items-center gap-1"}```|Star icon svg element
...attrs|string|```{class:"flex items-center gap-1"}```|apply any html attribute like 'class', 'id', or 'style' to the rating container
