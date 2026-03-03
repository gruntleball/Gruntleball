$(document).ready(function() { // testing
  $('#join-form').validate({
    rules: {
			"Email": {
        required: true,
        email:    true
			},
      "Zip Code": {
        required: true,
        zip_code: true
      }
		},
		messages: {
			"Zip Code": {
        required:  "Invalid zip",
         zip_code: "Invalid zip"
      },
			"Email": {
        required: "Invalid email",
        email:    "Invalid email"
      }
		},
    onkeyup: false,
    onfocusout: function(element) {$(element).valid();},
    errorElement: "strong",
		errorPlacement: function(error, element){
			var label = $( $(element).parents('form')[0] ).find('label[for="' + $(element).attr('id') + '"]');
			error.appendTo( label );
		},
    submitHandler: function(form){
      //console.log("submit handler");
      form.submit();
      $('#join-form').fadeOut("slow", function() {
        $('#join-form-response').fadeIn();
      });
    }
  
  });
	
  autoFillForm();
  
  function getParameterByName(name) {
    window.location.hash ? string = window.location.hash : string = window.location.search
    name = name.replace(/[\[]/, "\\[").replace(/[\]]/, "\\]");
    var regex = new RegExp("[\\?&]" + name + "=([^&#]*)"),
    results = regex.exec(string);
    return results === null ? "" : decodeURIComponent(results[1].replace(/\+/g, " "));
  }
  
  function autoFillForm() {
      var FirstNameParam = getParameterByName("firstname");
      var LastNameParam = getParameterByName("lastname");
      var EmailParam = getParameterByName("email");
      var ZipParam = getParameterByName("zip");
      
      if(FirstNameParam){
        $("#firstname").val(FirstNameParam);
      }
      if(LastNameParam){
        $("#lastname").val(LastNameParam);
      }
      if(EmailParam){
        $("#email").val(EmailParam);
        $("#emailaddress").val(EmailParam);
      }
      if(ZipParam){
        $("#zip").val(ZipParam);
        $("#postalcode").val(ZipParam);
      }
    }
  
});
