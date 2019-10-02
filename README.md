# VOJ Ajax Form
> **VOJ Ajax Form** is a jQuery Plugin that handle ajax requests of forms with minimum configurations ( be it a simple formor a multipart form ).
**Every feedback is welcome!**

## Installation
Include jQuery
https://jquery.com
```html
<script type="text/javascript" src="jquery.min.js"></script>
```
Include Bootstrap:
https://getbootstrap.com
```html
<link rel="stylesheet" type="text/css" href="bootstrap.min.css" />
<script type="text/javascript" src="bootstrap.min.js"></script>
```
Include Toastr-master( For Displaying Error/Success Messages):
https://codeseven.github.io/toastr
```html
<link rel="stylesheet" type="text/css" href="toastr.min.css" />
<script type="text/javascript" src="toastr.min.js"></script>
```

Include Plugin File:
```html
<script type="text/javascript" src="jquery.ajax-form.min.js"></script>
```

## Usage
Initialize Plugin
```javascript
$("#form").ajaxSubmit();
```
if form contains any file
```javascript
$("#form").ajaxSubmit({
  formdata:"filetype"
});
```

## Possible Configurations
```javascript
//default settings
var settings = {
  url : form.attr("action"),
	method: form.attr("method"),
	successCallback: function(data){
	  form.find('input, button, select, textarea').prop('disabled', false);
		if(data.success == true){
      toastr.success(data.message)
		}else{
		  toastr.error(data.message)
		}				
	},
	formdata: form.serialize(), // or "filetype"
	datatype: 'JSON',
	processdata: false,
	contenttype: false
}
$("#form").ajaxSubmit(settings);
```


## License

VOJ Ajax Form is licensed under the MIT license. (http://opensource.org/licenses/MIT)
