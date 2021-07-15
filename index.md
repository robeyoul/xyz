---
# FLEX
___
flex হলো one dimensional layout system।
অর্থাৎ আপনি যেকোন একদিকে কাজ করতে পারবেন হয় row বরারব না হয় কলাম বরাবর। flex এর অনেক গুলো প্রপার্টি আছে । কিছু প্রপার্টি parent div এর সাথে বসে আবার কিছু প্রপার্টি আছে যেগুলো child items এর সাথে বসে।

```html
<div class="parent-div">
   <div class="child-div"> child div 1</div>
   <div class="child-div"> child div 2</div>
   <div class="child-div"> child div 3</div>
</div>
```
---
# যে প্রপার্টি গুলো parent div এ বসে তাদের তালিকা নিম্নে দেয়া হলো:
___

1. প্রথমেই parent div এর ডিসপ্লে প্রপার্টিকে flex করতে হবে। flex না করলে কোন flex প্রপার্টি কাজ করবে না।

```css
.parent-class{
   display: flex;
}
```
## 2. flex-wrap:  
      ধরি আমাদের একটি parent div আছে যার width 1000px। এই parent div এর মধ্যে 12টি child div আছে।যাদের প্রতিটির width 100px করে। এখন ভাবুন আমরা জানি flex সাধারনত ডিফল্ট ভাবে row নিয়ে কাজ করে। তাহলে আমাদের 12টি child div কিন্তু আমাদের parent div কে ছড়িয়ে যাবে ।কারণ parent div এর width 1000px । আর child div গুলো মোট 1200px।   তাই আমরা যদি চাই যে যখন child div গুলো আর জায়গা পাবে না তখন তা নিচে নেমে আসবে তখন আমরা  flex-wrap ব্যাবহার করব।
---
### flex-wrap এর ভ্যালু তিনটি:
___

| value   |  description              |
|---------|--------------------------|
| no-wrap | এটি ডিফল্ট ভ্যালু। এর মানে child div গুলো কোন wrap হবে না। জায়গা না পেলে parent div পার হয়ে যাবে।
| wrap    | এর মনে যদি জায়গা না পায় তাহলে child div গুলো নিচে চলে আসবে।
| wrap-reverse | এটি wrap এর মতই তবে এর মাধ্যমে child div যেগুলো নিচে চলে আসবে সেগুলো রিভার্স হবে ।মনে প্রথমটি শেষে যাবে শেষেরটা প্রথমে আসবে।

```css
.parent-class{
   display: flex;
   flex-wrap: no-wrap;
}
```
```css
.parent-class{
   display: flex;
   flex-direction: wrap;
}
```
```css
.parent-class{
   display: flex;
   flex-direction: wrap-reverse;
}
```



##  3. flex-direction:
      আগেই বলেছি flex default ভাবে row বরাবর কাজ করে। 
      কিন্তু সবসময় আমরা যে row বরাবর কাজ করি বা করব এমন নয়। তাই যখন আমরা direction পরিবর্তন করতে চাইব তখন এই প্রপার্টি ব্যাবহার করব। এর ভ্যালু 3 টি।

| value   |  description              |
|---------|--------------------------|
| row     | এটি ডিফল্ট ভ্যালু।
| column  | আমরা যদি কলাম বরাবর কাজ করতে চাই তাহলে ভ্যালু কলাম দিব। কলাম দিলে প্রতিটি child div একটির নিচে একটি থাকবে।
| column-reverse |  এটি কলাম এর মতই। কিন্তু এই ভ্যালু ব্যাবহার করলে প্রতিটি child div রিভার্স হয় যাবে। অর্থাৎ যদি 3 টি div থাকে তাহলে 3নং টি প্রথমে, 2নং টি দ্বিতীয়তে, 1নং টি তৃতীয়তে বসবে ।


```css
.parent-class{
   display: flex;
   flex-direction: row;
}
```

```css
.parent-class{
   display: flex;
   flex-direction: column;
}
```

```css
.parent-class{
   display: flex;
   flex-direction: column-reverse;
}
```

# shortcut

আমরা চাইলে flex-wrap ও flex-direction কে এক সাথে লিখতে পারি। যেমন:

```css
.parent-div{
   display: flex;
   flex-flow: flex-wrap | flex-direction;
}
```

## 4. justify-content:
      justify-content সাধারনত horizontally align করার জন্য ব্যাবহার করা হয়।
      #### এর ভ্যালু 7টি:

```css
.parent-class{
   display: flex;
   justify-content: flex-start;
}
```

```css
.parent-class{
   display: flex;
   justify-content: flex-end;
}
```

```css
.parent-class{
   display: flex;
   justify-content: center;
}
```

```css
.parent-class{
   display: flex;
   justify-content: space-between;
}
```

```css
.parent-class{
   display: flex;
   justify-content: space-around;
}
```

```css
.parent-class{
   display: flex;
   justify-content: space-evenly;
}
```


| value        |       description          |
|--------------|----------------------------|
| flex-start   | **flex-start** মানে child div গুলো horizontally একদম শুরুতে থাকবে।|
| flex-srart   | **flex-end** মানে child div গুলো horizontally একদম শেষে থাকব।|
|   center     | **center** মানে child div গুলো horizontally একদম মধ্যখানে থাকবে।|
|space-between | **space-between** মানে child div গুলোর মধ্যে সমান ভাবে স্পেস থাকবে (horizontally)|
|space-around  | **space-around** মানে child div গুলোর ডানে,বামে সমান ভাবে স্পেস থাকবে (horizontally)|
|space-evenly  | **space-evenly** মানে child div গুলোর ডানে,বামে, উপরে,নিচে সব জায়গায় সমান ভাবে স্পেস থাকবে।|




## 5. align-items :
align-items সাধারনত vertically  align করার জন্য ব্যাবহার করা হয়।
#### এর ভ্যালু 7টি:

```css
.parent-class{
   display: flex;
   align-items: flex-start;
}
```

```css
.parent-class{
   display: flex;
   align-items: flex-end;
}
```

```css
.parent-class{
   display: flex;
   align-items: center;
}
```

```css
.parent-class{
   display: flex;
   align-items: space-between;
}
```

```css
.parent-class{
   display: flex;
   align-items: space-around;
}
```

```css
.parent-class{
   display: flex;
   align-items: space-evenly;
}
```


| value        |       description          |
|--------------|----------------------------|
| flex-start   | **flex-start** মানে child div গুলো vertically একদম শুরুতে থাকবে।|
| flex-srart   | **flex-end** মানে child div গুলো vertically একদম শেষে থাকব।|
|   center     | **center** মানে child div গুলো vertically একদম মধ্যখানে থাকবে।|
|space-between | **space-between** মানে child div গুলোর মধ্যে সমান ভাবে স্পেস থাকবে (vertically)|
|space-around  | **space-around** মানে child div গুলোর ডানে,বামে সমান ভাবে স্পেস থাকবে (vertically)|
|space-evenly  | **space-evenly** মানে child div গুলোর ডানে,বামে, উপরে,নিচে সব জায়গায় সমান ভাবে স্পেস থাকবে।|



___
#  এবাব আমরা আরো কিছু প্রপার্টি দেখব যেগুলো child-div এর সাথে বসে।

সাধারনত child-div এর সাথে চারটি প্রপার্টি বেশি বসে।
1. order
2. grow
3. shrink
4. flex-basis


## 1. order
```html
<div class="parent-div">
   <div class="child-1"> Div 1</div>
   <div class="child-2"> Div 2</div>
   <div class="child-3"> Div 3</div>
</div>
```
সাধারণভাবে উপরের কোডে প্রথমে Div 1 , তারপর Div 2 , তারপর Div 3 কে দেখবে। কিন্তু আমরা যদি এমন চাই যে, Div 3 কে সেকেন্ড পজিশনে এবং Div 2 কে থার্ড পজিশনে নিয়ে যাব। তাহলে আমাদের order use করতে হবে।

```css
.parent-div{
   display: flex;
}

.child-1{
   order: 0;
}
.child-2{
   order: 2;
}
.child-3{
   order: 1;
}
```

ডিফল্টভাবে order এর মান 0 থাকে।  অর্ডারের মান যত ছোট হবে সেই item তত আগে বসবে। উপরে আমরা যেহেতু child-1 এর অর্ডার 0 দিয়েছি তাই এর পজিশন পরিবর্তন হবে না। আবার child-2 ও child-3 এর অর্ডার দিয়েছি যথাক্রমে 2 ও 1। যেহেতু child-3 এর অর্ডারের মান child-2 থেকে ছোট। তাই child-3 আগে আসবে এবং child-2 পরে যাবে।
অর্থাৎ তখন দেখাবে Div 1, Div 3, Div 2 এইভাবে।


##  2. flex-grow

আমরা যদি parent-div এর মধ্যে থাকা child-div গুলোকে grow বা বড় করতে চাই তাহলে এই প্রপার্টি ব্যাবহার করব। 
flex-grow ডিফল্ট ভাবে 0 থাকে। 

## 3. shrink

shrink সাধারনত flex-grow এর বিপরীত। এর ডিফল্ট ভ্যালু 1 থাকে।

##  4. flex-basis

flex-basis দিয়ে সাধারনত child-div গুলোর width set করা হয়।  flex-basis দিয়ে child-div গুলোর min-width কত হবে টা সেট করা যায়। তবে মনে রাখতে হবে flex-basis আর min-width এক নয়। 
অর্থাৎ যদি এমন হয়:

```css
.parent-div{
   display: flex;
   width: 200px;
}

.child-div_1{
   flex-basis: 200px;
}

.child-div_2{
   flex-basis: 300;
}
```
এখানে parent div এর উইথ 200px । তাই child-div_1 পুরো 200px width ই নিবে।  যদি width 200 থেকে কমে যায় তাহলে child-div_1 ও অটোমেটিক কমে যাবে।
আবার child-div_2 এর width 300px কিন্তু parent-div 200px। এখন কিন্তু child div 2 300px হবে না। এটি 200px হয় যাবে।
অর্থাৎ imoortent পয়েন্ট হলো flex-basis কখনো parent-div এর width থেকে বেশি হবে না। আপনি মান বেশি দিলেও সেটা parent div এর width এর সমান হবে। overflow এর সমস্যা হবে না।
