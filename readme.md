vue-top-scroll
================

Simple customizable Vue component to add anywhere for a responsive "back to top" button.

![Alt Text](https://media.giphy.com/media/YzQaAyoNoOjWYFmsgJ/giphy.gif)


Installation
----------------------------------
`npm i vue-top-scroll`

Basic Usage
----------------------------------

* Register the component in your main app.js or equivalent file, eg:

```javascript
import TopScroll from 'vue-top-scroll';

Vue.component('top-scroll', TopScroll);
```

* Once registered you can just add it to any component

```html

<top-scroll></top-scroll>
```

* The look and behavior can be modified by passing different [props](#available-props)
  (see [available props](#available-props) for details)


* By default it uses font awesome 5 `far fa-angle-up` icon but you can pass an `icon` prop with anything else

[](#available-props)Available props
----------------------------------

You can either use the component as it is or pass some extra arguments in case you want to customize it. None of the
props is required

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| color | #e91e63 | String | The button background color |
| icon | far fa-angle-up | String | The button icon |
| size | 60px | String | Size of the button |
| font | 32px | String | Icon font-size |
| fontcolor | #fff | String | Icon color |
| visibleoffset | 600 | [String, Number] | Offset (`pageYOffset`) from top of when the icon should show up |
| right | 50px | String | Position from the right edge |
| bottom | 80px | String | Position from the bottom |

* Customized example

```html

<top-scroll color="#0091ea"
            icon="glyphicon glyphicon-chevron-up"
            size="50px"
            font="25px"
            fontcolor="#000"
            visibleoffset="900"
            right="10px"
            bottom="30px">
</top-scroll>
```

![Alt Text](https://media.giphy.com/media/cq4li91wKk2I4K90A2/giphy.gif)

