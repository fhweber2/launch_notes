###JS Triggering Events:

Script Tag belongs at the bottom of the markup - "we want the user to get the presentation of the markup first. then place all of the js scripts after"

This is because we want the markup to load before any JavaScript starts to load. It should be considered best practice to have any JavaScript be the last part of your body.

Placing the scripts (like below) allow for better page caching:
    
    markup, then scripts
    <!DOCTYPE html>
        blah 
            blah
        blah
        
         <script src ="http://ajax.googleapis.com......."
         
JS Debugger (like binding.pry)

    debugger;
    
________

    console.log //will break  IE6, 7
    
    //  Race Conditions
    
__________

    event.preventDefault(); 
     // prevents the default submission event 
     
'Chosen' to decorate checkboxes, radio buttons

ex:

    <input id="da-checkbox" value="it's checked" />
    
    $('a.sample-link').on('click', function(event){
        if($('#da-checkbox').is(':checked')){
          alert($('#da-checkbox').val()):
        }
        
        else {
            alert ('it is not checked')
        }
    });;

    
    


