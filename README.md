# Javascript Best Practices - collection


01. Declare variables outside loops	
02. Reduce DOM operation

	function processArray(myArray){
		var div = document.getElementById("container");
		var message = "";
		for(var i = 0; i < myArray.lenght; i++ ){
			message = message + myArray[i];
		}

		div.innerHTML = message;
	}

