# Astro-Rating

An Astro component for displaying the rate of something using stars

## Example:

![rating](https://raw.githubusercontent.com/BryceRussell/astro-rating/main/rating.PNG "Rating")

```<Rating total="90876" rate="2" max="5" />```

## How to use?

- Move the two star images to your public/imgs directory

- Import component and set props

## Props

__total__:

  - The total number of ratings Ex: 578, 6792, 14, etc

__max__:

  - Rate scale maximum Ex 5, 10 etc

__rate__:

  - Rate, a number between 0 and the max rate scale. Ex: 2, 4, 7, 8, etc

__enabled_src__:

  - Path to enabled star image source

__disabled_src__:

  - Path to disabled star image source


