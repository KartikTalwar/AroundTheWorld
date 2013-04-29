# Around the World - CSS3


## Overview

We will be learning about CSS3 and the cool animation effects, to create an animation of a man going around the world!

![](http://i.imgur.com/OdsIvaf.png)


### [Click here for the final demo](http://codepen.io/anon/pen/yjLrH)

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

Inspired by [this](http://codepen.io/pixelgrid/pen/suflz)

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

#### Animating the Bird

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

### Creating Sun

```html
<div class="container">
  <div class="earth"></div>
  <div class="bird"></div>

  <div class="sky">
    <div class="sun"></div>
  </div>

</div>
```

```css
.sky {
  position: absolute;
  left: 10%;
}

.sun {
    border-top: 5px solid #FFFF19;
    border-left: 5px solid #FFFF5E;
    border-right: 5px solid #FFFF33;
    border-bottom: 5px solid #FFFF00;
    border-radius: 100%;
    padding: 3px;
    animation: spin 5s linear infinite;
}
```

![](http://i.imgur.com/mTGKhdR.png)


#### Making the sun bigger

![](http://i.imgur.com/K8xngHv.png)

```html
<div class="sky">
  <div class="sun">
    <div class="sun">
      <div class="sun">
        <div class="sun">
          <div class="sun"></div>
        </div>
      </div>
    </div>
  </div>
</div>
```

**inception!**


### Adding a tree

![](http://i.imgur.com/Q2JiIn4.png)


```html
<div class="container">
  <div class="earth"></div>
  <div class="bird"></div>

  <div class="sky">
    <div class="sun">
      <div class="sun">
        <div class="sun">
          <div class="sun">
            <div class="sun"></div>
          </div>
        </div>
      </div>
    </div>
   </div>

  <div class="tree"></div>
</div>
```

```css
.tree {
  width: 300px;
  height: 300px;
  background: url('http://tinyurl.com/cdtree1');
  position: absolute;
  top: 50px;
  left: 100px;
  transform-origin: 50% 500px;
  animation: spin 12s linear infinite;
}
```

### Adding an Airplane

![](http://i.imgur.com/QYv4IHt.png)

```html
<div class="container">
  <div class="earth"></div>
  <div class="bird"></div>

  <div class="sky">
    <div class="sun">
      <div class="sun">
        <div class="sun">
          <div class="sun">
            <div class="sun"></div>
          </div>
        </div>
      </div>
    </div>
   </div>

  <div class="tree"></div>
  <div class="airplane"></div>
</div>
```

```css
.airplane {
  position: absolute;
  left: 30%;
  top: 10%;
  width: 150px;
  height: 100px;
  background: url('http://tinyurl.com/cdplane1') no-repeat;
  background-size: 150px 50px;
  transform-origin: 50% 500px;
  animation: spin 9s linear infinite;
}
```


### Adding the running boy


![](http://i.imgur.com/kxtvegN.png)


```html
<div class="boy"></div>
```

```css
.boy {
  height: 195px;
  background: url("http://tinyurl.com/cdrunning");
  animation: run .5s steps(8) infinite;
}

@keyframes run {
  0% { background-position: 0px; }
  100% { background-position: -960px; }
}
```

#### Adding the running effect

![](http://i.imgur.com/St5zMsB.png)

```html
<div class="container">
  <div class="earth"></div>
  <div class="bird"></div>

  <div class="sky">
    <div class="sun">
      <div class="sun">
        <div class="sun">
          <div class="sun">
            <div class="sun"></div>
          </div>
        </div>
      </div>
    </div>
   </div>
  

  <div class="tree"></div>
  <div class="airplane"></div>

  <div class="run">
    <div class="boy"></div>
  </div>

  
</div>
```

```css
.run {
  position: absolute;
  left: 40%;
  top: 30%;
  width: 120px;
  height: 195px;
  overflow: hidden; 
}
```

### [Click here for the final demo](http://codepen.io/anon/pen/yjLrH)


### Adding the cloud

```html
 <div class="cloud"></div>
```

```css
.cloud {
  margin-top: 100px;
  margin-left: 180px;
  transform-origin: 50% 400px;
  width: 150px;
  height: 60px;
  background: #f2f9fe;
  border-radius: 100px;
  position: relative;
  z-index: 0;
  animation: spin 7s linear infinite;
}

.cloud:after, .cloud:before {
  content: '';
  position: absolute;
  background: #f2f9fe;
  z-index: -1;
}

.cloud:after {
  width: 60px;
  height: 60px;
  top: -30px;
  left: 70px;
  border-radius: 100px;
}

.cloud:before {
  width: 80px;
  height: 80px;
  top: -40px;
  right: 50px;
  border-radius: 200px;
}
```


## Customizations


### Replace the current planet with map of the Earth
  
- Do you really need the `repeat` property?

### Make it night time

- Can we change the Sun's colors to make it look like the moon?
- Can we change the sky's color?

### Make the boy run backwards

- If positive direction is forward, what direction is backwards?


## Homework

Try converting this to a CSS and HTML document (outside of codepen)

You need to import this javascript file:

```html
<script src="http://leaverou.github.io/prefixfree/prefixfree.js"></script>
```

