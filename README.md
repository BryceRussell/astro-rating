# Astro-Rating

An Astro component for displaying the rate of something using stars

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

### Example:

![rating](/rating.png?raw=true "Rating")

`<Rating total="90876" rate="2" max="5" />`


