

# שאלות הכנה לראיון עבודה בג׳אווה סקריפט , אהבתם ? תנו ⭐

<div dir="rtl">

| No.      | Question |
| ----------- | ----------- |
| 1      | [מהם הדרכים האפשריות ליצור אובייקיט בjs](#ש-מהם-הדרכים-האפשריות-ליצור-אובייקט-בjs)       |
| 2   | [prototype chain מהו ה?](#שמהו-הprototype-chain-)        |
| 3   | [Call,Apply,Bind מה ההבדל בין ? ](#שמה-ההבדל-בין-callapplybind-) |
| 4   | [מהו JSON ומהם הפעולות הנפוצות שלו](#ש-מהו-json-ומהם-הפעולות-הנפוצות-שלו-)|
| 5   | [למה משמשת הפונקציה Slice?](#ש-למה-משמשת-הפונקציה-slice-)|
| 6   | [למה משמשת הפונקציה Splice ?](#ש-למה-משמשת-הפונקציה-splice-)|
| 7   | [מה ההבדל בין האופרטר == ל===?](#ש-מה-ההבדל-בין-האופרטר--ל)|
| 8   | [מהם Arrow functions ?](#ש-מהם-arrow-functions-)|
| 9   | [מהו first class function ?](#ש-מהו-first-class-function-)|
| 10  | [מהי high order function?](#ש-מהי-high-order-function)|
| 11  | [מהי פונקציה אונרית (unary function) ?](#ש-מהי-פונקציה-אונרית-unary-function-)|
| 12  | [מהי Currying function ?](#ש-מהי-currying-function-)|
| 13  | [מהי פונקציה טהורה ( Pure fucntion ) ?](#ש-מהי-פונקציה-טהורה--pure-fucntion--)|
| 14  | [מהו מנגון הHoisting ?](#ש-מהו-מנגון-הhoisting-)|
| 15  | [מהו הסקופ (scope) בג'אווה סקריפט ?](#ש-מהו-הסקופ-scope-בגאווה-סקריפט-)|
| 16  | [מה מטרתה של מילת המפתח let ?](#ש-מה-מטרתה-של-מילת-המפתח-let-)|
| 17  | [מה ההבדל בין let לvar ?](#ש-מה-ההבדל-בין-let-לvar-)|
| 18  | [מהו הTemporal Dead Zone ?](#ש-מהו-הtemporal-dead-zone-)|
| 19  | [מהי IFFE(Immediately Invoked Function Expression) ?](#ש-מהי-iffeimmediately-invoked-function-expression-)|
| 20  | []()|
| 21  | []()|
| 22  | []()|
| 23  | []()|
| 24  | []()|
| 25  | []()|

</div>

## ש. מהם הדרכים האפשריות ליצור אובייקט בJS?

יש מספר רב של דרכים ליצחר אובייקט בjs נמנה אותן:


1.Object constructor :
    
הדרך הפשוטה ביותר ליצור אובייקט ריק היא באמצעות בנאי של אובייקט , הדרך הזו לא מומלצת.
    
    
```js
    
var object = new Object();
    
```

2.Object's create method:

פונקציית היצירה של אובייקט יוצרת אובייקט חדש ע״י העברה של אובייקט הפרוטוטייפ כפרמטר 

```js

var object = Object.create(null);


```


3.Object's literal syntax :

אובייקט מילולי שהסינטקס שלו הוא סט של שם וערך מוםרד ע״י פסיק ועטוף בסוגריים מסולסלים

```js

var object = {
     name: "Shimi",
     age: 28
};


```

נשים לב שאובייקט מילולי יכול להיות מכל סוג שהוא  , כולל מערכים , פונקציות ואובייקטים מקוננים
    
4.Function constuctor:

יוצרים פונציה ומשתמשים באופרטור new על מנת ליצור מופע של האובייקט

```js
    
  function Person(name) {
  this.name = name;
  this.age = 21;
}
var object = new Person("Shimi");
    
    
```


5.Function constructor with prototype:

דומה לבנאי פונקציה אבל זה משתמש בפרוטוטייפ בשביל התכונות והמטודות.
	
	```js
	
	
function Person() {}
Person.prototype.name = "Shimi";
var object = new Person();
	
	
	```

	
6.ES6 class syntax:
	
בES6 אפשר ליצור אובייקט באמצעות תכונה של המחחלקה 
	
```js
	
	class Person {
  constructor(name) {
    this.name = name;
  }
}

var object = new Person("Shimi");
	
	
```


7.Singleton pattern:

סינגלטון הוא אובייקט שניתן לאתחל פעם אחת. קריאות חוזרות לבנאי שלו יחזירו את אותו האובייקט ובדרך הזה ניתן לוודא שהן לא יוצרות מספר מופעים 
	
```js

var object = new (function () {
  this.name = "Shimi";
})();
	

```


## ש.מהו הprototype chain ?

שרשרת פרוטוטייפ משמשת לבניה של סוגי אובייקטים חדשים אשר מתבססים על אובייקטים קיימים. זה דומה לירושה בשפות מבוססות מחלקות.

הפרוטוטייפ של מופע של אובייקט זמין דרך Object.getProtoTypeOf(object).


## ש.מה ההבדל בין Call,Apply,Bind ?

**Call** :  הפונקציה Call מפעילה פונקציה עם Owner Object כפרמטר , ופרמטרים נוספים שמועברים אחד אחד.


```js

var employee1 = { firstName: "John", lastName: "Rodson" };
var employee2 = { firstName: "Jimmy", lastName: "Baily" };

function invite(greeting1, greeting2) {
  console.log(
    greeting1 + " " + this.firstName + " " + this.lastName + ", " + greeting2
  );
}

invite.call(employee1, "Hello", "How are you?"); // Hello John Rodson, How are you?
invite.call(employee2, "Hello", "How are you?"); // Hello Jimmy Baily, How are you?




```


**Apply**: דומה לCall רק שכאן הארגומטים מסופקים כמערך 

```js

var employee1 = { firstName: "John", lastName: "Rodson" };
var employee2 = { firstName: "Jimmy", lastName: "Baily" };

function invite(greeting1, greeting2) {
  console.log(
    greeting1 + " " + this.firstName + " " + this.lastName + ", " + greeting2
  );
}

invite.apply(employee1, ["Hello", "How are you?"]); // Hello John Rodson, How are you?
invite.apply(employee2, ["Hello", "How are you?"]); // Hello Jimmy Baily, How are you?



```


**Bind** : מחזיר פונקציה חדשה , מה שמאפשר להעביר מספר ארגומנטים כרצוננו.


```js

var employee1 = { firstName: "John", lastName: "Rodson" };
var employee2 = { firstName: "Jimmy", lastName: "Baily" };

function invite(greeting1, greeting2) {
  console.log(
    greeting1 + " " + this.firstName + " " + this.lastName + ", " + greeting2
  );
}

var inviteEmployee1 = invite.bind(employee1);
var inviteEmployee2 = invite.bind(employee2);
inviteEmployee1("Hello", "How are you?"); // Hello John Rodson, How are you?
inviteEmployee2("Hello", "How are you?"); // Hello Jimmy Baily, How are you?



```

Call וApply די ניתנים להחלפה , שניהם מבצעים את הקוד באופן מיידי.המפתח צריך להחליט האם קל יותר עבורו להעביר את הפרמטרים אחד אחד או במערך.
בעוד Bind יוצרת פונקציה חדשה שתגדיר את this להיות הפרמטר הראשון שמועבר אליה.


## ש. מהו JSON ומהם הפעולות הנפוצות שלו ? 

ת.JSON לוקח את המבנה הפשוט של אובייקט JavaScript 
ומשתמש בו לאחסון מידע בפורמט שכל שפות המחשב יודעות לעבוד איתו.

העובדה שהמבנה של JSON זהה בכל שפות המחשב מאפשר לנו להעביר מידע בין מחשבים ללא קשר לשפה שבה כתובה האפליקציה. בהתאם לכך, רוב ה-API המודרניים שדרכם אנחנו מקבלים שירותים ברשת האינטרנט, דוגמת: מפות גוגל, אפליקציות מזג אוויר, או מערכות תשלומים משתמשים ב-JSON.


**Parsing:** ממיר סטרינג לאובייקט 

```js


JSON.parse(text);

```

**Stringification:** ממיר אובייקט לסטרינג כדי שנוכל להעביר אותו ברשת


```js

JSON.stringify(object);

```


## ש. למה משמשת הפונקציה Slice ? 

ת. הפונקציה Slice() מחזירה את האלמנטים הנבחרים במערך כאובייקט מערך חדש. היא בוחרת את האלמנטים שמתחילים בארגומנט ההתחלה הנתון ומסתיימת בארגומנט הסיום האופציונלי מבלי לכלול את האלמנט האחרון . אם לא מעבירים ארגומנט שני אזי הוא בוחר עד הסוף.

```js

let arrayIntegers = [1, 2, 3, 4, 5];
let arrayIntegers1 = arrayIntegers.slice(0, 2); // returns [1,2]
let arrayIntegers2 = arrayIntegers.slice(2, 3); // returns [3]
let arrayIntegers3 = arrayIntegers.slice(4); //returns [5]


```

נשים לב הפונקציה slice לא משנה את המערך המקורי אלא מחזירה תת מערך חדש.

## ש. למה משמשת הפונקציה Splice ? 
ת. הפונקציה Splice משמשת להוספה/מחיקה של איברים מ/ל מערך ולאחר מכן מחזירה את האיבר שהוסר.
הארגומנט הראשון מציין את המיקום שבו נרצה להכניס / ממנו נרצה למחוק את האיבר , הארגומנט השני או אופציונלי והוא מציין מספר האלמנטים שנרצה למחוק . כל ארגומנט נוסף יתווסף למערך.


```js

let arrayIntegersOriginal1 = [1, 2, 3, 4, 5];
let arrayIntegersOriginal2 = [1, 2, 3, 4, 5];
let arrayIntegersOriginal3 = [1, 2, 3, 4, 5];

let arrayIntegers1 = arrayIntegersOriginal1.splice(0, 2); // returns [1, 2]; original array: [3, 4, 5]
let arrayIntegers2 = arrayIntegersOriginal2.splice(3); // returns [4, 5]; original array: [1, 2, 3]
let arrayIntegers3 = arrayIntegersOriginal3.splice(3, 1, "a", "b", "c"); //returns [4]; original array: [1, 2, 3, "a", "b", "c", 5]

```

נשים לב שהפונקציה Splice משנה את המערך המקורי ומחזירה מערך עם האיברים שנמחקו.


## ש. מה ההבדל בין האופרטר == ל===?

ג׳אווה סקריפט מספקת בדיקת שיוויון קפדנית (strict) ע״י האופרטורים ===.!== וגם כזאת שהיא לא קפדנית באמצעות האופטורים == , != . השיטה הקפדנית לוקחת בחשבון גם את סוג המשתנים המושווים בעוד השיטה הלא קפדנית לוקחת בחשבון אך ורק את הערך . השיטה הפקדנית מקיימת את התנאים הבאים :

א. שני מחזורות הם שווים אם יש להם את אותה סדרה של תווים , באותו האורך ועם אותם תווים במיקומים המתאימים. 
ב.שני מספרים שווים אם הם שווים מספרית , כלומר יש להם את אותו ערך מספרי. ישנם שני מקרים מיוחדים :
	1.הערך NaN לא שווה לשום ערך אחר כולל Nan .
	2.אפס חיובי ושלילי שווים אח לשני
ג.שני אופרנדים בוליאניים שווים אם שניהם אמת או שניהם שקר.
ד.שני אובייקטים הם שווים אם הם מצביעים לאותו אובייקט.
ה.הערכים Null וUndefined לא שווים עם ===  אבל כן שווים עם == .

```js

0 == false   // true
0 === false  // false
1 == "1"     // true
1 === "1"    // false
null == undefined // true
null === undefined // false
'0' == false // true
'0' === false // false
[]==[] or []===[] //false, refer different objects in memory
{}=={} or {}==={} //false, refer different objects in memory


```

## ש. מהם Arrow functions ?

ת. Arrow Functions הם גרסה מקוצרת לפונקציות המסורתיות הרגילות עם מעט הבדלים סמנטיים ומגבלות שימוש - אין להן this,arguments,super משל עצמן.
הפונקציות הללו מתאימות ביותר לפונקציותש שהן אינן מתודות , כמו כן הן לא יכולות לשמש כבנאים (constructors) .

שימוש מסורתי בפונקציה : 

```js


hello = function() {
  return "Hello World!";
}


```

שימוש בפונקציית Arrow :

```js

hello = function() {
  return "Hello World!";
}


```

## ש. מהו first class function ?

בג'אווה סקריפט פונקציות הן אובייקטים first class . המשמעות של פונקציות שהן first class הוא שבשפה מתייחסים אליהן כמו כל משתנה אחר.

לדוגמה , בשפה כזו , ניתן להעביר פונקציה כפרמטר לפונקציות אחרות , אפשר להחזיר פונקציות ע"י פונקציה אחרת ואפשר לעשות השמה של פונקציה למשתנה. 
נמחיש בדוגמה : הפונקציה handler מוקצה למאזין (listener)

```js
const handler = () => console.log("This is a click handler function");
document.addEventListener("click", handler);

```

## ש. מהי first order function ? 
ת. First-order function היא פונקציה שלא מקבלת פונקציה כפרמטר ולא מחזירה פונקציה . 

```js

const firstOrder = () => console.log("I am a first order function!");

```
## ש. מהי high order function? 

ת. High-Order function זו פונקציה שמקבלת פונקציה כפרמטר או מחזירה פונקציה או שניהם יחד.

```js


const firstOrderFunc = () =>
  console.log("Hello, I am a First order function");
const higherOrder = (ReturnFirstOrderFunc) => ReturnFirstOrderFunc();
higherOrder(firstOrderFunc);


```



## ש. מהי פונקציה אונרית (unary function) ?

פונקציה אונרית היא פונקציה שמקבלת בדיוק ארגומנט אחד .

```js

const unaryFunction = (a) => console.log(a + 10); // Add 10 to the given argument and display the value


```

## ש. מהי Currying function ?

ת.Currying זהו תהליך שבו לוקחים פונקציה שמקבלת מספר פרמטרים והופכים אותה לסדרת פונקציות שכל אחת מהן מקבלת פרמטר אחד . Currying נקרא על שם המתטיקאי הסקל קורי .
```js

const multiArgFunction = (a, b, c) => a + b + c;
console.log(multiArgFunction(1, 2, 3)); // 6

const curryUnaryFunction = (a) => (b) => (c) => a + b + c;
curryUnaryFunction(1); // returns a function: b => c =>  1 + b + c
curryUnaryFunction(1)(2); // returns a function: c => 3 + c
curryUnaryFunction(1)(2)(3); // returns the number 6


```

## ש. מהי פונקציה טהורה ( Pure fucntion ) ? 
ת. פונקציה טהורה היא פונקציה שהערך המוחזר שלה נקבע ע"י הפרמטרים שלה בלבד , כלומר אם נקרא לפונקציה x פעמים עם אותם פרמטרים מx מקומות בתכנית היא תמיד תחזיר את אותו הערך . 

```js

//Impure
let numberArray = [];
const impureAddNumber = (number) => numberArray.push(number);
//Pure
const pureAddNumber = (number) => (argNumberArray) =>
  argNumberArray.concat([number]);

//Display the results
console.log(impureAddNumber(6)); // returns 1
console.log(numberArray); // returns [6]
console.log(pureAddNumber(7)(numberArray)); // returns [6, 7]
console.log(numberArray); // returns [6]


```
נסביר את הקוד לעיל , הPush היא פונקציה לא טהורה לכשלעצמה מאחר והיא משנה את המערך והיא מחזירה מספר אינדקס שלא תלוי בפרמטרים שהיא מקבלת.
בעוד שConcat לוקחת את המערכים , משרשרת אותם ומחזירה מערך משורשר ללא תופעות לוואי (side effects) , המערך המוחזר הוא שרשור של המערך הקודם.


## ש. מהו מנגון הHoisting ?

ת. Hoisting בג'אווה סקריפט זהו מנגון שבו , הצהרות על משתנים ,פונקציות ומחלקות מועברות לתחילת הסקופ שלהם לפני ביצוע הקוד. צריך לזכור שהמנגון עובד על הצהרות לא על אתחולים. נראה כמה דוגמאות פשוטות :

```js

// program to display value
a = 5;
console.log(a);// יודפס 5
var a; // 5

```
בדוגמה לעיל ניתן לראות שהכרזנו על a אחרי הlog ועדיין הודפס 5.

כלומר המפרשן (interpeter) רואה את זה כך :

```js

// program to display value
var a;
a = 5;
console.log(a); // 5


```

כאמור המנגון אינו עובד על אתחולים ולכן התוצאה של הקוד הבא יהיה undefined :

```js


// program to display value
console.log(a);
var a = 5;



```

## ש. מהו הסקופ (scope) בג'אווה סקריפט ?

ת. הסקופ הוא הנגישות של משתנים , פונקציות ואובייקטים בחלקים מסויימים של התכנית במהלך זמן הריצה. במילים אחרות הסקופ קובע את הנראות של משתנים ומשאבים אחרים באיזורים של הקוד.

אפשר למנות שלושה סקופים עיקריים:


* global - סקופ שמכיל וגלוי לכל הסקופים , על מנת להכריז על משתנה בסקופ זה צריך להצהיר עליו חוץ לפונקציה או באמצעות אובייקט הwindow.
* function - סקופ המוקנה לקטעי קוד שנמצאים בתוך פונקציה
* block - קטעי קוד שתחומים בסוגריים מסולסלים {} .

נראה דוגמאות :
הכרזה על משתנה באמצעות אובייקט החלון : 

```js

window.value = 90;

// הצהרה על משתנה גלובלי באמצעות אובייקט החלון
function setValue() {
  window.value = 100;
}

// גישה למשתנה הגלובלי מפונקציה אחרת
function getValue() {
  setValue();
  return window.value;
}

console.log(getValue()); // 100


```

דוגמה לבלוק סקופ :

```js

{
  let x = 2;
}

```

דוגמה לסקופ של פונקציה :

```js

function myFunction() {
  var carName = "Volvo";   // Function Scope
}




```






## ש. מה מטרתה של מילת המפתח let ? 
ההצרה let מכריזה על משתנה מקומי במרחב הבלוק ( block scope ) . כלומר המשתנים המוגדרים באמצעות let מוגבלים למרחב הבלוק , או הביטוי שעליו הוא נכתב. בעוד שמשתנים שהוצרו באמצעות מילת המפתח var משמשים להגדרת משתנים גלוביים או לכל מרחב הפונקציה ללא קשר למרחב הבלוק. נראה דוגמה :
```js

let counter = 30;
if (counter === 30) {
  let counter = 31;
  console.log(counter); // 31
}
console.log(counter); // 30 (בגלל שהמשתנה בבלוק לא קיים כאן)


```

## ש. מה ההבדל בין let לvar ?

נפרט את ההבדלים ע"י טבלה : 

| var      | let |
| ----------- | ----------- |
| קיים מההתחלה של ג'אווהסקריפט      | הוצג בגרסה ES6       |
| סקופ של פונקציה   | סקופ של בלוק        |
| המשתנים יעברו Hoisting   | המשתנים יעברו Hoisting אבל לא יאותחלו        |



נראה דוגמה שממחישה את ההבדל :

```js
function userDetails(username) {
  if (username) {
    console.log(salary); // undefined כתוצאה מהHoisting
    console.log(age); // שגיאת רפרנס: לא ניתן לגשת למשתנה 'age' לפני האתחול
    let age = 30;
    var salary = 10000;
  }
  console.log(salary); //10000 ניתן לגשת כי לvar יש סקופ של פונקציה
  console.log(age); //שגיאה , age הוא לא מוגדר כיוון שלlet יש סקופ של בלוק
}
userDetails("John");

```
## ש. מהו הTemporal Dead Zone ?

ת. Temporal Dead Zone זהו התנהגות של ג'אווה סקריפט שקוראת כאשר מכריזים על משתנה עם מילות המפתח let וconst ולא עם var . בECMAscript 6 , אם ניגשים למשתנים שהוכרזו ע"י let או const לפני ההצהרה עליהם ( ובתוך הסקופ שלהם ) גורם לשגיאת רפרנס . טווח הזמן שבו זה קורה , בין יצירת הbinding של המשתנה וההצהרה שלו נקרא הTemporal dead Zone. נראה זאת באמצעות דוגמה:

```js
function somemethod() {
  console.log(counter1); // לא מוגדר
  console.log(counter2); // שגיאת רפרנס
  var counter1 = 1;
  let counter2 = 2;
}


```

## ש. מהי IFFE(Immediately Invoked Function Expression) ?
ת. IFFE היא פונקציה בג'אווה סקריפט שרצה ברגע שהיא מוגדרת. החתימה שלה תהיה כדלהלן :

```js

(function () {
  // logic here
})();


```
הסיבה העיקרית לשימוש בIIFFE היא לשמור על פרטיות של של נתונים מאחר שלא ניתן לגשת למשתנים שהוגדרו בתוך הIIFFE , אם ננסה נקבל שגיאה כמו בדוגמה הבאה :

```js

(function () {
  var message = "IIFE";
  console.log(message);
})();
console.log(message); //שגיאה : Message לא מוגדר



```
## ש. מהם מחלקות בES6 ? 

ת. בES6 , המחלקות הן בעיקר [סוכר תחבירי](https://he.wikipedia.org/wiki/%D7%A1%D7%95%D7%9B%D7%A8_%D7%AA%D7%97%D7%91%D7%99%D7%A8%D7%99) של ירושה באמצעות פרוטוטייפ .
לדוגמה ירושה באמצעות פרוטוטייפ יכתב כך :

```js
function Bike(model, color) {
  this.model = model;
  this.color = color;
}

Bike.prototype.getDetails = function () {
  return this.model + " bike has" + this.color + " color";
};

```

בעוד שמחלקה בES6 תראה כך :

```js

class Bike {
  constructor(color, model) {
    this.color = color;
    this.model = model;
  }

  getDetails() {
    return this.model + " bike has" + this.color + " color";
  }
}

```

