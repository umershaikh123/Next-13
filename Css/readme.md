# css cheatsheet

### Clamp

```
Clamp(min , preferred , max);
width : Clamp(200px , 50% , 400px);
width : Clamp(45ch , 50% , 75ch);

```

### Aspect Ratio

```
aspect ratio: 16/9

```

### Variables


```
:root {

    --variable-Name: rgb(0,0,0);
} 


p {
    color : var(--variable-Name);
}

h {
    --variable-Name : green ; //override variable 
    color : var(--variable-Name);
}


```


### calc()

```

width : calc(100vh - 200px)
width : calc(100vh + 200px)
width : calc(100vh * 200px)
animation-delay : calc(var(--order * 100 ms))

```

### order
```
"--order : 1"
"--order : 2"
"--order : 3"
```

