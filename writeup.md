# Box-Model

It's a very important part of Css . According to the box model, every element is a rectangular box on a page and it may have some width, height, padding, borders, and margins. Before going to box-model I want to tell about the Display property . Display property has some properties e.i. inline, inline-block, block and none. So we have inline and block level element by default . We can use "display" property with the value "inline-block" and "none" to the element for some better experience.

* Inline : Generally some element is inline-level by default . For example span, strong, b etc. These elements support only padding left & right, border left & right and margin left & right. These also support padding top & bottom and border top & bottom but it's bleed to the previous and next element.

* Block : Some element is block-level element by default. For example p, div, h1...h6 etc. These type of elements supports all the properties that is width , height, padding, margin , border .

![image](https://raw.githubusercontent.com/suraj122/AC-STYLE-images/master/box-model/box-model-table.png)

## Properties included in Box-Model

Box-Model includes width, height, border, margin and padding property .

### Width

Every element has some default width based on the display property. If it is a block-level element it will have 100% width covering whole horizontal space. If it is an inline or inline-block element it will have width according to the content it wraps.

```
div {
   width: 300px;
 }
 ```

### Height

As every element has some default width in a similar way every element also has some default height and that is always determined by its content.

```
div {
    height: 300px;
  }
```

### Padding

 The padding property is applied to provide space around the content, within an element.

> Padding for all inside (shorthand)
```
 div {
    padding: 20px;
  }
```

> Padding 20px is for top and bottom , padding 40px is for left and right [First value is for vertical padding and second value is for horizontal padding]

```
 div {
    padding: 20px 40px;
  }
```

> Padding in a clock wise direction , first one is for top , second one is for right , third one is for bottom and fourth one is for left Padding.

```
 div {
    padding: 10px 0 20px 30px;
  }
```

>In the longhand properties, we can set value for one side at a time.

```
 div {
    padding-top: 10px;
    padding-right: 0;
    padding-bottom: 20px;
    padding-left: 30px;
  }
```

### Border

The border is to provide some outline around an element. To apply border we have border property which requires three different values: border-width, border-style, and border-color.

```
div {
    border: 10px solid red;
  }
```

### Margin

Margin property is applied to provide a gap between the elements on a page. It provides space around the element. So from the above code, there will be space of 20px around the element. It can be also used to position the element on the page.
The margin property is very similar to padding. But instead of applying inside the element, it sets the space that surrounds outside the element.
We can apply the margin to a element like the padding.


> There are two another properties included in the box-model that is box-shadow and outline . Explain below :

### Box-shadow

The property generally accepts five values. The first four values are for creating length and height of shadow and the last value is for the color of the shadow. The first value is for the shadow's offset in the horizontal direction, the second value is for the shadow's offset in the vertical direction, the third value is for blur radius. The third value determines how blurry the shadow will look. The fourth value is to spread the shadow in all directions. This is the optional value, without this also we can create a shadow.


 ```
 div {
    box-shadow: 3px 3px 6px rgba(0, 0, 0, 0.3);
  }
 ```

 We can use multiple shadows also separating by coma "," :

 ```
 div {
   box-shadow: 3px 3px 6px rgba(0, 0, 0, 0.3), 6px 6px 10px rgba(0, 0, 0, 0.3);
 }
 ```

 If we provide the values in negative then it will create a shadow in the opposite direction.

 ```
 div {
    box-shadow: -3px -3px 6px rgba(0, 0, 0, 0.3);
  }
 ```

 To create some solid line around the box using box-shadow we can only provide spread value and color value. Rest of the value will be 0.

 ```
 div {
    box-shadow: 0 0 0 3px #000;
  }
 ```

 All the above box-shadow values will create the shadow outside the box, but if you want to create the shadow inside the box you can just add inset at the starting of the value.

 ```
  div {
    box-shadow: inset 3px 3px 6px rgba(0, 0, 0, 0.3);
  }
  ```

### Outline

Apart from all the box model properties, there is a property, outline, that draws a line around the elements, outside the borders.

```
div {
    outline: 10px solid blue;
  }
 ```

* It won’t affect the position of the element or adjacent elements. Also it is not counted while calculating the size of an element.

* There is no outline-top, outline-right, outline-bottom, or outline-left like there is with border.


## The Box Sizing Property

However, we can change the default box model of an element. In CSS there is another property, box-sizing which allows us to change how the box model works and how an element's size is calculated. The box-sizing property accepts two different values, content-box and border-box.

### Content Box

The content-box value for the box-sizing property is the default value, that leaves box model property additive only. If we do not specify any box-sizing property for an element, that means the model is still content-box.

```
div {
    box-sizing: content-box;
  }
```

In content box after the width and height, whatever the extra properties padding, borders, or margins we define will get added to determine the exact size of the box.

```
div {
   margin: 20px;
   width: 300px;
   height: 200px;
   padding: 20px;
   border: 10px solid #272727;
   box-sizing: content-box;
 }
 ```
 OR

 ```
 div {
    margin: 20px;
    width: 300px;
    height: 200px;
    padding: 20px;
    border: 10px solid #272727;
  }
  ```
In the above div total size of the box will be :

Total width = margin-left + border-left + padding-left + width + padding-right + border-right + margin-right = (20px + 10px + 20px + 300px + 20px + 10px + 20px) = 400px


Total height = margin-top + border-top + padding-top + width + padding-bottom + border-bottom + margin-bottom = (20px + 10px + 20px + 200px + 20px + 10px + 20px) = 300px


### Border Box

Border box value changes the box model. It keeps the padding and border within the specified width and height.

```
div {
   margin: 20px;
   width: 300px;
   height: 200px;
   padding: 20px;
   border: 10px solid #272727;
   box-sizing: border-box;
 }
 ```
In the above div total size of the box will be :

Total width = margin-left + width + margin-right = (20px + 300px + 20px) = 340px

Total height = margin-top + width + margin-bottom = (20px + 200px + 20px) = 240px

## Developer Tools

we can inspect window has HTML elements on the left side and the right side style related to the HTML elements. In Chrome, on the top left corner of the inspect window, you also get a button to select any element on the page. Clicking that button you can select any element on the page by clicking on it. Once you select an element on the page, all the styles related to that element will be revealed on the right side.

It is very useful to see the box-model of any element . If we make a mistake then we can inspect the element and see the box-model.
