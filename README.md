

# שאלות הכנה לראיון עבודה בג׳אווה סקריפט , אהבתם ? תנו ⭐


| No.      | Question |
| ----------- | ----------- |
| 1      | [מהם הדרכים האפשריות ליצור אובייקיט בjs](#ש-מהם-הדרכים-האפשריות-ליצור-אובייקט-בjs)       |
| Paragraph   | Text        |

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




