

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
| 13  | []()|
| 14  | []()|
| 15  | []()|
| 16  | []()|
| 17  | []()|

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
ת. פונקציה טהורה היא פונקציה שהערך המוחזר שלה נקבע ע"י הפרמטרים שלה בלבד , כלומר אם נקרא לפונקציה x פעמים מx מקומות בתכנית היא תמיד תחזיר את אותו הערך . 

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
