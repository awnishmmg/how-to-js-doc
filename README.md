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
			<div class="row mt-2">
			    <div class="col-md-2"><b>Add Parameter <span style="color:red;font-weight: bold;"><span style="color:red;font-weight: bold;">*</span></span></b></div>
			    <div class="col-md-10" style="overflow-y: auto;max-height: 300px;">
			       	<table class="table table-striped table-bordered">
			       		
			       			<thead style="background-color: black;color:white;position: sticky;top:0;">
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
			        </div>
			</div>
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

### Javascript code to convert Any Normal Text Data to Invoice with #prefixed code

```
//convert to Invoice with prefix #
function converttoInvoice(element){
  that = element;
  if(that.value == ""){
    return true;
  }else{
    var Oldvalue = that.value;
    if(Oldvalue[0]!="#"){ that.value = "#"+Oldvalue; }
    else{ that.value = Oldvalue; }
  }
  
}
```
### Function to Dynamically Change Class in Upward and Downward

```

function ChangeArrow(element){

  if($(element).find("i").hasClass("fa-arrow-down")){
      
      $(element).find("i").removeClass("fa-arrow-down");
      $(element).find("i").addClass("fa-arrow-up");
  }else{

      $(element).find("i").removeClass("fa-arrow-up");
      $(element).find("i").addClass("fa-arrow-down");
  } 

}

```
