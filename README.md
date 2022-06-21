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

#### Font Awesome

![Font Awesome](https://raw.githubusercontent.com/BryceRussell/astro-rating/main/examples/font-awesome.PNG)

```
const font_awesome = {
  rate: "8.5",
  max: "10",
  total: "32769",
  starFull: "ph:star-fill",
  starHalf: "ph:star-half-fill",
  starDisabled: "ph:star",
  iconClass: "text-yellow-500 w-4 h-4"
}

<Rating {...font_awesome}/>
```

#### Material Design Icons

![Material Design](https://raw.githubusercontent.com/BryceRussell/astro-rating/main/examples/material-design.PNG)

```
const material_design = {
  rate: "2.5",
  max: "5",
  total: "72",
  starFull: "mdi:star",
  starHalf: "mdi:star-half-full",
  starDisabled: "mdi:star-outline",
  iconClass: "text-yellow-500 w-4 h-4"
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
  containerClass: "flex flex-col-reverse items-end",
}

<Rating {...col-reverse}/>
```

![Reversed Row](https://raw.githubusercontent.com/BryceRussell/astro-rating/main/examples/row-reversed.PNG)

```
const row-reverse = {
  rate="2.5" 
  max="5"
  total="178"
  containerClass: "flex flex-row-reverse items-center gap-1",
}

<Rating {...row-reverse}/>
```

## Props

Propname | Type | Description | Default
------------ | ------------- | ------------- | -------------
rate|number\|string|0|# between 0 and max
max|number\|string|5|max number of stars|5
total|number\|string||total # of ratings
starFull|string|star-full|[astro-icon](https://github.com/natemoo-re/astro-icon#readme) Icon name prop representing a full star
starHalf|string|star-half|[astro-icon](https://github.com/natemoo-re/astro-icon#readme) Icon name prop representing a half star
starDisabled|string|star-disabled|[astro-icon](https://github.com/natemoo-re/astro-icon#readme) Icon name prop representing a disabled star
containerClass|string|flex items-center gap-1|class of the entire rating componenet
totalClass|string|leading-none text-xs text-gray-300|class of the total ratings span element
starsClass|string|flex items-center|class to div that holds all stars
iconClass|string|h-4 w-4|class to div that surrounds the icons svg element
