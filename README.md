

# שאלות הכנה לראיון עבודה בג׳אווה סקריפט , אהבתם ? תנו ⭐

<div dir="rtl">

|    שאלה   | מספר |
| ----------- | ----------- |
| 1      | דגדגדג       |
| 1   | גדשגשד        |



## ש. מהם הדרכים האפשריות ליצור אובייקט בJS?

יש מספר רב של דרכים ליצחר אובייקט בjs נמנה אותן:


1.Object constructor :
    
    הדרך הפשוטה ביותר ליצור אובייקט ריק היא באמצעות בנאי של אובייקט , הדרך הזו לא מומלצת.
    
    ׳׳׳js
    
    var object = new Object();
    
    ׳׳׳

2.Object's create method:

פונקציית היצירה של אובייקט יוצרת אובייקט חדש ע״י העברה של אובייקט הפרוטוטייפ כפרמטר 

׳׳׳js

var object = Object.create(null);


׳׳׳


3.Object's literal syntax :

אובייקט מילולי שהסינטקס שלו הוא סט של שם וערך מוםרד ע״י פסיק ועטוף בסוגריים מסולסלים

׳׳׳js

var object = {
     name: "Shimi",
     age: 28
};


׳׳׳

נשים לב שאובייקט מילולי יכול להיות מכל סוג שהוא  , כולל מערכים , פונקציות ואובייקטים מקוננים


יוצרים פונציה ומשתמשים באופרטור new על מנת ליצור מופע של האובייקט

׳׳׳








</div>

<div dir="rtl">

## ש. מהי פונקציה אנונימית?

פונקציה אנונימית היא פונקציה שאין שם שמשויך אליה. ניתן לגשת לפונקציה אנונימית אך ורק ע"י משתנה שמאחסן את הפונקציה.

4.Function constructor:

׳׳׳




**דוגמה:**

<div dir="ltr">

```js
function() {
    // Function Body
 }
 
```
 ניתן גם להצהיר על פונקציה אנונימית באמצעות Arrow Functions :
```
 ( () => {
    // Function Body...
} )();

```


**דוגמאות נוספות : **

בדוגמה זו אנחנו מגדירים פונקציה אנונימית שמדפיסה הודעה לconsole , הפונקציה מאוחסנת במשתנה greet , ניתן לקרוא לפונקציה באמצעות קריאה לgreet()
```js
let greet = function () {
    console.log("Welcome to GeeksforGeeks!");
};
 
greet();

```

<div/>

## ש. כמה ומהם סוגי נתונים הקיימים בג'אווה סקריפט ?

קיימים שני סוגי נתונים , פרימיטיביים ולא פרימיטיביים.


## ש. מהם סוגי הנתונים הפרימיטיביים בג'אווה סקריפט ?

1.String.<br>
2.Number.<br>
3.Boolean.<br>
4.BigInt.<br>
5.Undefined.<br>
6.Null.<br>
7.Symbol.<br>

## ש. מהם סוגי המשתנים הלא פרימיטביים בג'אווה סקריפט ?

1.Object


## ש. מה ההבדל בין == ל === ?

== בודק רק שיוויון בעוד === בודק גם את סוג המשתנה

נראה דוגמה:


<div dir="ltr">

```js
let a = 10;
let b = '10';
let c = 10;

console.log(a==b);
//output true;

console.log(a===b);
//output: false;

console.log(a===c);
//output: true;

```
<div/>

## ש. מה ההבדל בין משתנה שהוא undeclared ל undefined ?

משתנה שהוא undeclared הוא בעצם משתנה שלא קיים בתוכנית ולא הצהרנו עליו בשום שלב , אם התוכנית תנסה לקרוא את הערך של משתנה לא מוצהר אנו ניתקל בשגיאת זמן ריצה , לעומת זאת משתנה שהוא undefined הוא משתנה שהצהרנו עליו אבל לא נתנו לו שום ערך , אם התוכנית נסה לקרוא את הערך ממשתנה שהוא undefined הערך undefined יוחזר לנו


## ש.מה הוא hoisting בג'אווה סקריפט ?

בג'אווה סקריפט משתנה יכול להיות מוצהר לאחר השימוש בו , hoisting זהו התהליך שבו הInterpeter מעביר את כל ההצהרות של המשתנים והפונקציות לתחילת הסקופ לפני ביצוע הקוד

<div dir="ltr">

```js
test = 5;
console.log(test);
var test;
//output: 5 

```

<div/>

נשים לב שlet וconst לא מאפשרים hoisting.

דוגמה נוספת לHoisting של פונקציה:

<div dir="ltr">

```js
greet();

function greet() {
    console.log('Hi, there.');
}

//output : Hi , there

```js
<div/>

## ?ש. מהם משתנים גלובליים

משתניים גלובליים מוכרזים מחוץ לפונקציה או מוכרזים ע"י window object והם נגישים לכל התכנית (אלא אם כן הוצללו (shadowed) ע"י מתשנה מקומי. אם נגדיר משתנה ללא var , const או let הוא יהיה גלובלי גם אם יוגדר בתוך פונקציה
נראה דוגמאות:

<div dir="ltr">

```js

var x = 10;

if (x === 10) {
  var x = 20;

  console.log(x);
  // expected output: 20
}

console.log(x);
// expected output: 20

```
<div/>

הגדרת משתנה גלובלי מתוך פונקציה עם window object :

<div dir="ltr">

```js

window.value = 90;

// Declaring global variable by window object
function setValue() {
  window.value = 100;
}

// Accessing global variable from other function
function getValue() {
  setValue();
  return window.value;
}

console.log(getValue()); // 100

```
</div>

בדוגמה הבאה נראה איך הגדרת משתנה ללא var , let , conts הופכת להיות משתנה גלובלי :

<div dir="ltr">

```js

function foo(arg) {
    bar = "this is a hidden global variable";
}

```

<div/>


זה בעצם זה:


```js

<div dir="ltr">

function foo(arg) {
    window.bar = "this is an explicit global variable";
}

```

נשים לב שבstrict mode לא ניתן להכריז על משתנים בצורה הזו , במידה ונעשה זאת נקבל שגיאה
<div/>








<div/>


