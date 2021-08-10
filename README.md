# how-to-js-doc
This is JavaScript Documentation.

### How to create Your Text Editor
```
<div class="col-md-6"><div name="message" class="editable" readonly><span style="font-weight: bold;"> Hi ! Administrator,</span>
 	A Per Request Please Integrate the Hooks Api. 
</div>
```
Add the JQuery Code
```
<script type="text/javascript">
	
	$(document).ready(function(){

		$('.editable').each(function(){
   	     this.contentEditable = true;

   	    $(".editable").each(function(){
   	    	$(this).css("border","2px solid silver");
   	    	$(this).css("outline","1px solid white");
   	    	$(this).css("overflow-y","scroll");
   	    	$(this).css("height","70px");
   	    	$(this).css("white-space","pre");
   	    	$(this).css("border-radius","2px");
   	    });
});
	});
	

</script>

```
