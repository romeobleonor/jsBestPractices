# Javascript Best Practices - collection and other important concept


01. Declare variables outside loops	
02. Reduce DOM operation

	```javascript
	function processArray(myArray){
		var div = document.getElementById("container");
		var message = "";

		for(var i = 0; i < myArray.length; i++) {
			message += myArray[i];
		}

		div.innerHTML = message;
	}	
	```
03. Choose short but readable variable names
04. Reduce or eliminate global variable to avoid name clashes. 
	Couple of ways to reduce potential name clashes are :
	* Put all the variables you need to define at the global level inside on global object
	  ```javascript
	     var My_Object = {
	     	name: "Romeo Leonor",
	     	showName: function(){
	     		return this.name;
	     	}
	     }
	  ```
	* Use a function to create **Closure** containing any variables/functions you need at the top level and return an object that provide access to the variables/functions. 
	  ```javascript
	     // closure
	     var My_Closure = (function(){
	     	// private method
	     	function changeName(val){
				return val + " - prefix";
	     	}
	     	return {
	     		name: "Romeo Leonor",
	     		setName : function(name){
					this.name = changeName(name);
	     		}
	     	}
	     })();

	     My_Closure.setName("Maya Hillary")
	  ```
05. Always use var to declare your variables and put the variables up at the top.
06. Indent your code so it's readable
07. Use curly braces to define blocks of code
08. Comment your code. 
09. **Function / Inheritance**
	* are just a kind of an object, when you creat a function, javascript create an object for you
	with 3 properties - the *name*, *arguments* and *prototype*

	```javascript
	// 1 - Create a parentObj as a prototype; will set the prototype later
	var parentObj = {parentId: "00 - Parent Property"}
	// Rather than creating a child object using Object.create(parentObj), let's create a constructor
	function ChildObj(value){
		this.childId = value;
	}
	// 2 - Before we create an instance for ChildObj, let's set the prototype to inherit the parentObj
	ChildObj.prototype = parentObj;
	// 3 - Now let's create an instance for ChildObj
	var son = new ChildObj("01 - child property");

	// 4 - let us test the son object
	console.log(son.parentId) // parentId property will be look up on parentObj
	console.log(son.childId) // childId property contained in son object
	```
10. -





    

