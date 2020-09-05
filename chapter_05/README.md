### Important Note
There is a change here, the following code will return 6 separate object, not in an array.  

	d3.csv("food.csv", function(data) {  
        console.log(data);  
    });  

Because [the csv function have changed since version 5.0](https://github.com/d3/d3/blob/master/CHANGES.md#changes-in-d3-50) and began to using a [promise](https://observablehq.com/@observablehq/introduction-to-promises) instead of asynchronous callbacks. We could change the code to:  

    d3.csv("food.csv")	
    .then(function(data) {	
        console.log(data);		
    })		
    .catch(function(error) {		
        console.log("There is some error when loading the data");		
    });  
	
[Other data loading methods](https://github.com/d3/d3-fetch) are also changed, such as [d3.json()](https://github.com/d3/d3-fetch#json) and [d3.text()](https://github.com/d3/d3-fetch#text)...

Reference: [https://stackoverflow.com/questions/49599691/how-to-load-data-from-a-csv-file-in-d3-v5](https://stackoverflow.com/questions/49599691/how-to-load-data-from-a-csv-file-in-d3-v5)

