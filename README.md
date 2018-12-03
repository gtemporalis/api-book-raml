# api-book-raml
Api Rest Book Design using RAML

Some examples of calls and outputs for each endpoint.

<b>PUT</b> http://localhost:8081/api/books/{isbn}<br>
	<b>200</b><br>
	    Parametro requerido {isbn}: ISBN-123456
			{"message": "The book has been successfully updated."}<br>
	<b>404</b><br>
	    Parametro requerido {isbn}: ISBN-12345 (Requerido)
			{"message" : "Unable to find book with that identifier"}<br>

<b>DELETE</b> http://localhost:8081/api/books/{isbn}<br>
	<b>200</b><br>
	    Parametro requerido {isbn}: ISBN-123456
			{"message" : "The book has been successfully removed."}<br>
	<b>404</b><br>
	    Parametro requerido {isbn}: ISBN-12345 (Requerido)
			{"message" : "Unable to find book with that identifier"}<br>

<b>GET</b> http://localhost:8081/api/books<br>
	<b>200</b><br>
	    Parametro opcional {lang}: en
			{
				"books": [
				  {
					"isbn": "ISBN-345341",  
					"title": "El Tunel",   
					"language": "es",      
					"authors": ["Ernesto Sábato"], 
					"year": 1990,          
					"pages": 350,          
					"prices": {            
					  "ar": 230.50,          
					  "ch": 703.0,
					  "br": 78.99
					}
				  },
				  {
					"isbn": "ISBN-345341",  
					"title": "Codigo DaVinci",   
					"language": "en",      
					"authors": ["Dan Brown"], 
					"year": 2002,          
					"pages": 2350,          
					"prices": {            
					  "ar": 450.50,          
					  "ch": 901.0,
					  "br": 450.71
					}
				  },
				  {
					"isbn": "ISBN-345341",  
					"title": "La voz ausente",   
					"language": "pt",      
					"authors": ["Gabriel Rolon"], 
					"year": 1982,          
					"pages": 890,          
					"prices": {            
					  "ar": 645.20,          
					  "ch": 237.0,
					  "br": 125.69
					} 
				  }
				]
			}<b>
	<b>404</b><br>
	    Parametro opcional {lang}: nr
			{}

<b>GET</b> http://localhost:8081/api/books/{isbn}<br>
	<b>200</b><br>
	    Parametro requerido {isbn}: ISBN-123456
			{
			  "isbn": "ISBN-345341",  
			  "title": "La voz ausente",   
			  "language": "pt",      
			  "authors": ["Gabriel Rolon"], 
			  "year": 1982,          
			  "pages": 890,          
			  "prices": {            
				"ar": 645.20,          
				"ch": 237.0,
				"br": 125.69
			  }
			}
	<b>404</b><br>
	    Parametro requerido {isbn}: ISBN-12345 (Requerido)
			{"message" : "Unable to find book with that identifier"}<br>

		
