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
03. Test

