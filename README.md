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

### Add & Remove Functionality using Table is the easiest way
```
<table class="table table-striped table-bordered">
			       		
			       			<thead style="background-color: black;color:white;">
			       				<tr>
				       				<th>Serial No.</th>
				       				<th>Parameter</th>
				       				<th>
				       					<button type="button" class="btn btn-warning btn-sm addmore" >
				       					Add More</button>

				       				</th>
			       				</tr>
			       			</thead>
			       		
			       		<tbody id="append-rows">
			       			
			       		</tbody>
			       			

			       	</table>
```

**Adding JQuery Code**
```
//code for Adding more and remove functionality
	
	var i = 1;
	$(document).ready(function(){
		$(".addmore").click(function(){
			$("#append-rows").append(`<tr>
					    <td>`+i+`.</td>
					    <td><input type="text" name="parameter[]" class="form-control"></td>
					    <td><button type="button" class="btn btn-danger btn-sm" onclick="removebtn(this);">Delete</button></td>
			  		</tr>`);
			i++;
		})
	});
	

	function removebtn(element){
		$(element).parent().parent().remove();
		i--;
	}

```
