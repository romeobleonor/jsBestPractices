# Javascript Best Practices - collection


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
05. xXXX

    

