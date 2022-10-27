

# javascript-interview-questions-hebrew

<div dir="rtl">

## ש. מהי פונקציה אנונימית?

פונקציה אנונימית היא פונקציה שאין שם שמשויך אליה. ניתן לגשת לפונקציה אנונימית אך ורק ע"י משתנה שמאחסן את הפונקציה.

**דוגמה:**

<div dir="ltr">

```
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
```
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

```
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

```
test = 5;
console.log(test);
var test;
//output: 5 

```

<div/>

נשים לב שlet וconst לא מאפשרים hoisting.

דוגמה נוספת לHoisting של פונקציה:

<div dir="ltr">

```
greet();

function greet() {
    console.log('Hi, there.');
}

//output : Hi , there

```
<div/>


<div/>


