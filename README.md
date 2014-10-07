visitors-bureau
===============
START from index.html. from there you'll have three options- login (visitor), login (employee, slightly hidden lowerleft of screen); or register. Limited functionality is simulated for the logged in user and logged in employee.

Deliverable #1: For each method supported by each resource in your service, specify what kinds of representation (if any) it requires, and what kinds of representations, including status codes, it might return. Be sure to consider possible error conditions. Add this specification to your repository.

For both visitors and employees: GET to the visitors bureau protected resource returns 401 Unauthorized response code, including a response header indicating what kind of credential is needed (e.g. a username/password); Client makes the GET request again, this time with the credential in a request header (metadata field); If the credentials are invalid, the server responds with 401
Unauthorized again; If the credentials are valid but the user doesn't have permission
to access the resource, the server responds with 403 Forbidden. Otherwise the server responds with 200 OK. (info gotten via email correspondence)

for visitor: 
            a GET occurs to access registration page from index.html. a POST follows entering all information in required fields. if you don't put in all fields you are prompted in the code to fill out all fields and cannot proceed until doing so. once completed user gets a 200OK.
            
            a GET to a favorites list returns a list of links to individual business resources, or the message No favorites yet.              status code is 200 OK.
        
            a PATCH occurs to add a business or event to the user's favorites list, status code 200 or 204 occurs. 

For employee/webmaster:
POST to Visitors Bureau business add/edit page returns the message Created business {business-name} with the URI of the new      business in the Location HTTP header, and a 201 Created status code. If the POSTed data is missing some required                  information (e.g. the business name), it returns the message business's name is required with a 400 Bad Request status             code.

POST to Visitors Bureau event add/edit page returns the message Created event {event-name} with the URI of the new event in the Location HTTP header, and a 201 Created status code. If the POSTed data is missing some required information (e.g. the event name or time/date), it returns the message event's name and time/date is required with a 400 Bad Request status code.

PUT to a Business resource requires a representation including (at least) the business’ name and URL. If either of these is    missing, the response will be the message business's {property} is required (repeated once for each missing property) with       a 400 Bad Request status code. If the business doesn’t exist yet, the response will be the message No such business exists      with a 404 Not Found error code. Otherwise the response will be the message Updated business {business-name} with a 200 OK status code.

PUT to a Event resource requires at least event name and time/date.  If these things are missing the user will receive a 400 Bad request status code. If it doesn't exist the user attempted to enter it they will receive a No such event exists message with 404 Not Found error code. Otherwise the event will be updated with 200 OK.

List of rel and class attributes

    rel
    edit-form
    used in employee view to indicate that forms can be used for editing
    
    class
    menu
    indicates a menu class for which specific styling will be applied
    
    business_body
    indicates the main portion of a business
    
    business_name
    name of the business to be styled and called according to specification
    
    business
    indicates a list item type "business"- all types of businesses- shops, bars, clubs, and restaurants- are included here.
    
    event_body
    indicates the event information will be included here
    
    event_name
    to be called/styled according to specification
    
    

    
