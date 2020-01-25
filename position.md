# Position: Static

The default position for all elements is position:static, which means the element is not positioned and occurs where it normally would in document. 

Noramlly you wouldnt specify this unless you needed to override a postion that had been previously set.

```css

#div-1 {
    position:static;
}

```

# Position relative

If you specify position relative, then you can use top or bottom, and left or right to move the elemen relative to where it normally occur in the document. 


Let's move div-1 down 20 px and to left 40px


```css

#div-1 {
    position:relative;
    top:20px;
    left:-40px;
}

```

as you did so, you may have notice the space where div-1 normally would have if we had not moved i: now it is an empty space. 

The next element did not moved when we moved div-1. That's becuase div-1 still occupies that original space in the document, even though we have moved it. 

It appears that postion: relative is not very useful, but it will perform an important task later in this tutorial.

# Position : Absolute

When you specify a position absolute, the element is removed from the document flow and placed where you tell it to go. 

Now let's move div-1a to the top-right of this page. 

```CSS 

    #div1-a {
        position:absolute;
        top:0;
        right:0;
        width:200px;
    }

```

Notice this time, since div-1a was removed from the document flow, the other elements on the page were positioned differently: div1-b, div1-c and div-after moved up since div-1a was no longer there. 

Also notice that div1-a was positioned on the top right corner of the page. It's nice to be able to position things directly to the page. but it's of limited value.

What i really want is to position div-1a relative to div-1. And that when position relative comes into play.


## Footnotes

- There is a bug in IE browser: of you specify a relative width (width:50%) then the width will based on the parent element instead of on the position element. 


# Position:Relative + position:Absolute 

If we set relative position on div-1, any elements wuthin div-1 will be positioned relative to div-1. Then if we set absolute position to div-1a, we can move it to the top right of div-1:

```css

#div-1 {
    position:relative;
}

#div-1a {
    position:absolute
    top:0;
    right:0;
    width:200px;
}

````

# 2 column absolute 

Now e can make two-column layout using relative and absolute positioning. 

One advantage of using absolute pos is that we can pos the elements in any order on the page regardless of how they appear in html So i put div1b before div1a.

But wait - what happend to other elements? Theya re being obscured by abslt posn els

what can we do about that?

# 2 column abslt height

One solution is to set a fixed height on elms

But that is not vialbe solution for most designs. Because we usuall dont know how much text will be there in the element. 



# Floats

For variable height cols, abs pos does not work. so lets come up with another solution. 

We can "float" an element to push it as far as possible to the right or left and allow text to wrap around it. 

This is typically used for images, but we will use it for more complex layout tasks. 

```CSS

#div-1a {
    float:left;
    width:200px;
} 


````