# how-to-js-doc
This is JavaScript Documentation.

### How to Add Morris.js Donuts Charts using formatter 

***In case of donut charts data has to binded in format of {labels:"",value:""}***
***To Empty the charts***

```
$('#sms-analysis').empty();

```
```
$return_array['application_data'] = $sms_count_data;

		$pieChartsData = [];
		foreach ($sms_count_data as $row) {

			$data_m[] = [
				'Delivered' => $row['delivered'],//85
				'Unprocessed' => $row['send']-$row['processed'],//10
				// 'Failed' => (($row['delivered']/$row['processed'])*100),
				'Failed' => ($row['processed']-$row['delivered']),//5
			];
		}

		foreach ($data_m as $index => $data_xy) {
			foreach ($data_xy as $label => $value) {
						$pieChartsData[] = [
						'label' => ucfirst($label),
						'value' => $value,
					];
			}
		}

```


```
var sum=0;
function PurchaseAnalysis(id='',data=[]){

if(data.length){

  for(var i=0;i<data.length;i++){
     sum =  parseInt(sum)+parseInt(data[i].value);
  }

//console.log(sum);
Morris.Donut({
  element: id,
  data:data,
  dataLabels:true,
  colors:['green','yellow','red'],
  resize:true,
  formatter:function(y,data){
    var count = y
    var percentage = (parseInt(count)/sum)*100
    if(isNaN(NaN)){percentage = 0};
    response_text = numberWithCommas(y)+"\n "+percentage.toFixed(2)+"%";
    return response_text;
  },

});

}else{
  $('#'+id).append('<label class="no-data-label">Sorry No Data Found!</label>');
     }
}


```


### Make a function in javascript to convert numberswithcommas in thousands.

```
function numberWithCommas(x) {
    x = x.toString();
    var pattern = /(-?\d+)(\d{3})/;
    while (pattern.test(x))
        x = x.replace(pattern, "$1,$2");
    return x;
}

```

# How to Make Preview Modal using Iframe to open, pdf, Images, vedios,

Add The Modal Form 
```

<div class="modal fade" id="previewDailogModal" tabindex="-1" role="dialog" aria-labelledby="previewDailogLabel" aria-hidden="true">
    <div class="modal-dialog" role="document" style="width: 100%;height: 100%;">
      <form action="" method="POST" id="previewDailog">
        <div class="modal-content">
          <div class="modal-header">
            <button type="button" class="close" data-dismiss="modal" aria-label="Close"> <span aria-hidden="true">&times;</span> </button>
            <h4 class="modal-title" id="previewDailogLabel"><b>Preview Invoice <span id="modal-invoice-no"></span></b></h4> </div>
          <div class="modal-body">
              <iframe src="" id="pdf-reader" frameborder="0" height="600" scrolling="no"width="100%"></iframe>          
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal">No,Go Back</button>
            <!-- <button type="submit" class="btn btn-danger">Yes Delete</button> -->
          </div>
        </div>
      </form>
    </div>
  </div>

```
Close Modal using Esc
```

$(document).keydown(function(event) { 
  if (event.keyCode == 27) { 
    $('##modal-invoice-no').modal("hide");
  }
});

```
Adding JQuery Trigger Event for Onclick
```

function previewDailog(url,element){

$("#pdf-reader").attr("src",url);
$("#previewDailogModal").modal("show");

$("#modal-invoice-no").html($(element).text());

}


```
Adding data in element
```
<td>
          <?php $total_path = base_url('assets/uploads/purchase_invoice/'); ?>

          <button onclick="previewDailog('<?php echo $total_path.$row['invoice']; ?>',this);" style="cursor: pointer;">
            <?php echo $row['invoice_no'];?>
          </button>

        </td>
```



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

### How to Disable Right Click 

```
//Disable Right Click of the Menu
document.addEventListener('contextmenu', event => event.preventDefault());
```
