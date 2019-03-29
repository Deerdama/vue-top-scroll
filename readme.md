vue-top-scroll
================

Simple customizable Vue component to add anywhere for a responsive "back to top" button. 

Installation
----------------------------------
`npm i vue-top-scroll`

Basic Usage
----------------------------------

* Register the component in your main app-vue.js file
```javascript
Vue.component('scroll-top', require('./components/ScrollTopComponent.vue'));
```

* Once registered you can just add it to any page
```html
<scroll-top></scroll-top>
```

* By default it uses font awesome 5 `far fa-angle-up` icon but you can pass an `:icon` prop with anything else 
(see [available props](#available-props) for details)

[](#available-props)Available props
----------------------------------

You can either use the component as it is or pass some extra arguments in case you want to customize it.
None of the props is required

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
<scroll-top :color="'#29a0ff'"
            :icon="'glyphicon glyphicon-chevron-up'"
            :size="'70px'"
            :font="'32px'"
            :fontcolor="'#000'"
            :visibleoffset="900">
</scroll-top>

```

