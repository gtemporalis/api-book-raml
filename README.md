# api-book-raml
Api Rest Book Design using RAML

Examples of calls and outputs for each endpoint.

PUT http://localhost:8081/api/books/{isbn}
	200
	    Parametro requerido {isbn}: ISBN-123456
			{"message": "The book has been successfully updated."}
	404
	    Parametro requerido {isbn}: ISBN-12345 (Requerido)
			{"message" : "Unable to find book with that identifier"}

DELETE http://localhost:8081/api/books/{isbn}
	200
	    Parametro requerido {isbn}: ISBN-123456
			{"message" : "The book has been successfully removed."}
	404
	    Parametro requerido {isbn}: ISBN-12345 (Requerido)
			{"message" : "Unable to find book with that identifier"}

GET http://localhost:8081/api/books
	200
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
			}
	404
	    Parametro opcional {lang}: nr
			{}

GET http://localhost:8081/api/books/{isbn}
	200
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
	404
	    Parametro requerido {isbn}: ISBN-12345 (Requerido)
			{"message" : "Unable to find book with that identifier"}

		

GET http://localhost:8081/api/authors
	200
		{
			"authors": [
			  {
				"id": "1",  
				"name": "Ernesto Sábato"
			  },
			  {
				"id": "2",  
				"name": "Dan Brown"
			  },
			  {
				"id": "3",  
				"name": "Gabriel Rolón"
			  }
			]
		}
	
	404
		{}

GET http://localhost:8081/api/authors/{authorname}
	200
		{
			"authors": [
			  {
				"isbn": "SBN-345341",
				"title": "El Tunel"
			  },
			  {
				"isbn": "SBN-345341",  
				"title": "Codigo DaVinci"
			  },
			  {
				"isbn": "SBN-345341",  
				"title": "La voz ausente"
			  }
			]
		}
	
	404
		{}
