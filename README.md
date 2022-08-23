# Always bottom footer using `Flexbox`

**[View the page live](https://rifayetuxbd.github.io/always-bottom-footer/)**

We can achieve the feature using two way:
1. Using `height` along with `flex-shrink`

1. Using `min-height`


### Using `height`
```css
#root {
    width: 100%;
    height: 100vh; /* Using height instead of min-height */
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
}

.header {
    height: 64px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.main {
    background-color: azure;
    color: darkblue;
    flex-grow: 1;

    padding: 20px;
}

.footer {
    height: 80px;
    border-top: 1px solid gray;
    display: flex;
    align-items: center;
    justify-content: center;
}

.header,
.main,
.footer {
    flex-shrink: 0; 
    /* 
    By default flex-shrink is set to 1, if we don't use 
    flex-shrink: 0 here header and footer will look weird
    as header and footer will take only the space it needs
    */
}
```

### Using `min-height`
```css
#root {
    width: 100%;
    min-height: 100vh; /* Using min-height instead of height */
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
}

.header {
    height: 64px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.main {
    background-color: azure;
    color: darkblue;
    flex-grow: 1;

    padding: 20px;
}

.footer {
    height: 80px;
    border-top: 1px solid gray;
    display: flex;
    align-items: center;
    justify-content: center;
}

/*
This time Don't need to use flex-shrink: 0
As it will maintain individual element height
*/
```

> Note: *I prefer using `min-height`*
