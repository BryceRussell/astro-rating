# Astro Rating :star: :star: :star: :star: :star:

A customizable Astro component that uses stars :star: to display the rating of a product, post, comment, etc

## Examples

NOTE: uses ```<img>``` tags to display stars

![Rating Component Example](https://raw.githubusercontent.com/BryceRussell/astro-rating/main/example.JPG)

## How to use

__Install package__:

```npm i astro-rating```

__Inside an .astro component/layout/page__:

```
import { Rating } from 'astro-rating';

//Create a rating
<Rating total="90876" rate="5" max="5" />

//Define your own star images, must be inside your ./public directory
<Rating total="90876" rate="5" max="5" enabled_src="imgs/star.webp" disabled_src="imgs/star_disabled.webp" />
```

## Props

Propname | Type | Description
------------ | ------------- | -------------
total|number\|string|total # of ratings
max|number\|string|max number of stars
rate|number\|string|# between 0 and max
enabled_src|string|enabled star image filepath inside the public directory Ex: imgs/star.webp
disabled_src|string|disabled star image filepath inside the public directory Ex: imgs/star_disabled.webp

## To-do
- __Bug__: Throws a ts(2307) module not found error when importing even though it works on dev server and build????
- Ability to use half points Ex: 4.5/5, 7.5/10, etc
- Class prop for class based styling
- Add more star options
