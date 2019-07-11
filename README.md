# Change-URL-Parameter-in-javascript


# Editing a Parameter
The set method of the URLSearchParams object sets the new value of the parameter.

After setting the new value you can get the new query string with the toString() method. This query string can be set as the new value of the search property of the URL object.

The final new url can then be retrieved with the toString() method of the URL object.

# --------------------------------------------------------------------
var url = new URL('http://demourl.com/path?id=100&topic=main');

var query_string = url.search;

var search_params = new URLSearchParams(query_string); 

// new value of "id" is set to "101"
search_params.set('id', '101');

// change the search property of the main url
url.search = search_params.toString();

// the new url string
var new_url = url.toString();

// output : http://demourl.com/path?id=101&topic=main
console.log(new_url);
# --------------------------------------------------------------------


# Adding a New Parameter
The set method can be used to add a new parameter as well - the parameter is added if it does exist, otherwise its value is changed.

The append method can be used to add multiple values to a parameter.
# --------------------------------------------------------------------
var url = new URL('http://demourl.com/path?id=100&topic=main');

var query_string = url.search;

var search_params = new URLSearchParams(query_string); 

search_params.append('id', '101');

search_params.append('id', '102');

url.search = search_params.toString();

var new_url = url.toString();

// output : http://demourl.com/path?id=100&id=101&id=102&topic=main
console.log(new_url);
# --------------------------------------------------------------------


# Deleting a Parameter
The delete method can be used to delete a parameter.

# --------------------------------------------------------------------
search_params.delete('id');
# --------------------------------------------------------------------
