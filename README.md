#MyRetail REST API
MyRetail RESTful service provides the client application ability to:
1.	Get Product Details by ProductId. (GET Request)
2.	Add new Products and persist to MongoDB db. (POST Request)
3.	Update Product using ProductId. (PUT Request)
##Get Product Details:
###Input: The client application does a GET request at the path "/products/{id}" for a product
###Internal Working: When API gets the request it extracts the product id from the request and sends a request to the database to fetch all the details of this Product and displays it to the user.
###Output: For a product with product id “3”, the sample JSON output is as shown below
{"id":3,"name":"product3","price":"1500"}
###Errors/Validations: Appropriate error messages are provided after validating the data. More information is available in the below sections. The client application can use the message in the response to display the same to the user appropriately.

##Add new Product Details:
####Input: 
The client application does a POST request at the path "/products" for a product
####Internal Working: 
When API gets the request, it checks if the product id already exists in the database. If it doesn’t then only new Product is created with the details mentioned by the user which are fetched from the Request body.
####Output: 
Here Product id 3 is being inserted, the sample JSON output is as shown below
{
	"id":3,
	"name":"product3",
	"price":"3000"
}
####Errors/Validations: 
Appropriate error messages are provided after validating the data. More information is available in the below sections. The client application can use the message in the response to display the same to the user appropriately.
##Update Product Price in the datastore:
####Input: 
The user/client application can do a PUT request with input similar to the response received in GET excluding the Product id. Product Id cannot be changed. User will be able to modify the price and the name in the datastore. The request is done at the same path "/products/{id}"
####Sample Input: 
JSON Body - {
	"price": "1500",
	"name": "product3"
}

####Internal Working: 
When the API receives a PUT request, it checks if the product exists in the database. If it does, the price for the product or name is modified in the data store.
####Output: 
Success message is returned if the product is modified.
####Errors/Validations: 
Appropriate error messages are provided after validating the data. More information is available in the below sections. The client application can use the message in the response to display the same to the user appropriately.
##Technologies Used
	1.	Spring Boot - https://projects.spring.io/spring-boot/
	2.	MongoDB - https://www.mongodb.com/
	3.	Postman - https://www.getpostman.com/
##Instructions to Setup
	1.	Install MongoDB in your system - https://docs.mongodb.com/manual/installation/
	2.	Run MongoDB - Run 'mongod.exe' in order to start Mongodb
	3.	Make sure you are in the myDb directory
	4.	Open postman. http://localhost:8080/product/1
	5.	Postman documentation explains the expected request and response for GET and PUT requests.
##Postman:
Postman displays the following information for an API method by default. 
 Type of request(GET/PUT/POST) and the path of request
	1.	Status and format of the response
	2.	Response Content Type
	3.	Parameters list
	4.	Possible Failure Responses with HTTP code

##Dependencies
	1. org.springframework.boot
	2. org.mongodb
	3. com.fasterxml.jackson.core
 




































































































