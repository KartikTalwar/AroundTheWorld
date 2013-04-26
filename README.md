# Around the World - CSS3


## Overview

We will be learning about CSS3 and the cool animation effects, to create an animation of a man going around the world!

![](http://i.imgur.com/OdsIvaf.png)


### [Click here for the final demo](http://codepen.io/anon/pen/rgcBl)

## Prerequisites

**Tools**

- [CodePen.io](http://codepen.io)

**Experience**

- Basic CSS skills
- Basic HTML skills

## Getting Started

### Creating a new Pen

Visit [codepen.io](http://codepen.io/) and click the "New Pen" button.

![](http://i.imgur.com/0zk5K1C.png)

### Setting up the environment

In the top right corner of each section, there is a gear button that will allow you to access the settings for that piece of code. We're going to make a few modifications to make sure our environment is ready for the code we are about to write.

#### CSS Settings

- Select "None" as the type of CSS.
- Select "Reset" to reset style and elminiate browser inconsistancies.
- Select "Prefix free" so you don't have to worry about vendor prefixes.
  - This doesn't matter too much for what we are doing but if you start experimenting towards the end, it may help.

![](http://i.imgur.com/u065kVg.png)


### Creating an empty container

**HTML**
```html
<div class="container">
</div>
```

**CSS**
```css
.container {
  width: 500px;
  height: 500px;
  margin: 0 auto;
  position: relative;
  border: 1px solid;  
  overflow: hidden;
  background: #6699CC;
}
```

### Creating Earth

```html
<div class="container">
  <div class="earth"></div>
</div>
```

```css
.earth {
  width: 500px;
  height: 500px;
  border-radius: 100%;  
  overflow: hidden;             
  background: url('http://tinyurl.com/cdearth1') repeat;
  background-size: 100px;
  position: absolute;
  top: 60%;
  left: 0px;
}
```

![](http://i.imgur.com/Ry6qmw8.png)

**Adding animation to Earth**

**CSS**

We declare a motion called `spin`

```css
@keyframes spin{ 100% { transform: rotate(360deg); } }
```

```css
...
animation: spin 10s linear infinite; 
...
```


### Creating a bird

![](http://i.imgur.com/CX2LEA7.png)

```html
<div class="container">
  <div class="earth"></div>
  <div class="bird"></div>
</div>
```

```css
.bird {
  background: black;
  border-radius: 50% 50% 20% 20%;
  position: absolute;
  top: 5%;
  left: 80%;
  margin-top: -20px;
  margin-left: -10px;
  width: 15px;
  height: 15px;
  animation: fly 0.8s linear infinite;
}
```


#### Adding wings to the bird

![](http://i.imgur.com/IWp3ETm.png)

```css
.bird:after, .bird:before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
}

.bird:after {
  border-radius: 100% 100% 0 0;
  box-shadow: inset 0px 5px 0px black;
  width: 100px;
  height: 100px;
  margin-top: -7px;
  margin-left: -50px;
  transform-origin: 100% 0%;
  animation: flap 3s linear infinite;
}
```

#### Animatng the Bird

```css
@keyframes flap {
  100% { transform: rotateX(1000deg); }
}
```

```css
@keyframes fly {
  50% { transform: translate3d(15px, 18px, 5px); }
}
```


## Customizations

**Samples**

## Additional Resources


## Homework
