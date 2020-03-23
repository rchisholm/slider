# VanillaSlider

VanillaSlider is a simple, lightweight, responsive slider using vanilla JavaScript, requiring no third-party libraries.

## Usage

To use VanillaSlider, first, embed the script in HTML:
```html
<script type='text/javascript' src='vanilla-slider.js'></script>
```
Then, define the slider container's id and the `options` object, and call `createSlider`:
```html
<script>
    var containerId = 'slider-1';

    var options = {
        transitionTime: 500,
        transitionZoom: 'in',
        bullets: true,
        arrows:true,
        arrowsHide: true,
        images: [
            'img/1.jpg',
            'img/2.jpg',
            'img/3.jpg',
            'img/4.jpg'
        ]
    }

    var slider = createSlider(containerId, options);
</script>
<div id='slider-1'></div>
```

## Live Examples

- [Slider using all custom options](https://rchisholm.github.io/vanilla-slider/docs/all-options.html)
- [Slider using only default options](https://rchisholm.github.io/vanilla-slider/docs/no-options.html)
- [Slider using the full browser width](https://rchisholm.github.io/vanilla-slider/docs/full-width.html)
- [Slider inside a div with a max width](https://rchisholm.github.io/vanilla-slider/docs/max-width.html)

## Parameters

### containerId
`containerId` is a required parameter. It can either be the element to be used as the container for the slider, or the element's id:
```javascript
var containerId = document.getElementById('slider=1');
```
```javascript
var containerId = 'slider=1';
```

### options
`options` is an optional parameter. If omitted, default values are used.
| Option | Type | Description | Default |
| --- | --- | --- | --- |
| images | Array<string\|object> | array of images, either strings (URLs) or objects with imageUrl, linkUrl, linkNewTab | null |
| transitionTime | number | time in ms until transition is finished; | 250 |
| transitionDirectionX | string | x direction for fading out element to move - 'left', 'right', or 'random' | null |
| transitionDirectionY | string | y direction for fading out element to move - 'up', 'down', or 'random' | null |
| transitionZoom | string | direction for zooming the fading out element - 'in', 'out', or 'random' | null |
| bullets | boolean | whether to show bullets | false |
| bulletsHide | boolean | whether to hide bullets on mouse out | false |
| bulletColor | string | color of active bullet | 'red' |
| arrows | boolean | whether to show arrows | true |
| arrowsHide | boolean | whether to hide arrow on mouse out | true |
| swipe | boolean | whether to allow swipe support | true |
| auto | boolean | whether to automatically move slides | false |
| autoTime | number | time in ms for slides to automatically move | 10000 | 

#### Sample of all options
```javascript
var options = {
    transitionTime: 1000,
    transitionDirectionX: 'left',
    transitionDirectionY: 'up',
    transitionZoom: 'in',
    bullets: true,
    bulletColor: 'blue',
    bulletsHide: true,
    arrows: true,
    arrowsHide: true,
    swipe: true,
    auto: true,
    autoTime: 5000,
    images: [
        'img/1.png',
        {
            imageUrl: 'img/2.png',
            linkUrl: 'https://www.github.com/'
        },
        'img/3.png',
        {
            imageUrl: 'img/4.jpg',
            linkUrl: 'https://www.github.com',
            linkNewTab: true
        },
        'img/5.jpg',
        {
            imageUrl: 'img/6.jpg'
        }
    ]
};
```

## Images
Images can be declared either by the `options.images` array or by images placed inside the container div:
```javascript
images: [
    'img/1.jpg',
    'img/2.jpg',
    'img/3.jpg'
]
```
```html
<div id='slider-1'>
    <img src='img/1.jpg'>
    <img src='img/2.jpg'>
    <img src='img/3.jpg'>
</div>
```

## Image Links
Images can have links associated with them. These links have the option of opening in a new tab. These can be declared either by properties in the `options.images` array or by anchor tags placed inside the container div:
```javascript
images: [
    'img/1.jpg',
    {
        imageUrl: 'img/2.jpg',
        linkUrl: 'https://www.github.com/'
    },
    {
        imageUrl: 'img/2.jpg',
        linkUrl: 'https://www.github.com/'
        linkNewTab: true
    }
]
```
```html
<div id='slider-1'>
    <img src='img/1.jpg'>
    <a href='https://www.github.com'>
        <img src='img/2.jpg'>
    </a>
    <a href='https://www.github.com' target='_blank'>
        <img src='img/3.jpg'>
    </a>
</div>
```

## Methods

#### getNextIndex
Get the index of the next slide.
```javascript
console.log(slider.getNextIndex());
// 1
```

#### getPrevIndex
Get the index of the previous slide.
```javascript
console.log(slider.getPrevSlide());
// 3
```

#### nextSlide
Go to the next slide.
```javascript
slider.nextSlide();
// moves to the next slide
```

#### prevSlide
Go to the previous slide.
```javascript
slider.prevSlide();
// moves to the previous slide
```

#### goToSlide
Go to the slide at the indicated index.
```javascript
slider.goToSlide(2);
// moves to the slide at index 2
```

#### startAuto
Begin automatic slide movement.
```javascript
slider.startAuto();
// starts auto slide movement
```

#### pauseAuto
Pause automatic slide movement until slides move manually.
```javascript
slider.pauseAuto();
// pauses auto slide movement until slides move 
```

#### stopAuto
Stop automatic slide movement.
```javascript
slider.stopAuto();
// stops auto slide movement
```

## Properties
Properties can be accessed after the VanillaSlider has been instantiated:

```javascript
console.log(slider.containerId);
// slider-1

console.log(slider);
// VanillaSlider {...}
```


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.


## License
[ISC](https://choosealicense.com/licenses/isc/)
