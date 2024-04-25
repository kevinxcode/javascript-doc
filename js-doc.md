# javascript-doc
javascript-doc


```
function dateShortFormat (date_data){
	const date = new Date(date_data);
	const formattedDate = date.toLocaleDateString('en-GB', {
  	day: 'numeric', month: 'short', year: 'numeric'
	}).replace(/ /g, ' ');
	return formattedDate;
	// console.log(formattedDate);
}
```

```
<?php echo ($contract_end_date ? date('d M Y', strtotime($contract_end_date)) : null) ?>
```

```
<span onclick="sayHi()" class="btn btn-primary btn-sm">Support Center</span>
<script>
	
	function sayHi() {
		load_tes();
		setTimeout(function() {
			Swal.close();
        }, 3500);
	}
	function load_tes(){
		Swal.fire({
        title: 'please wait..',
        html: '',
        // timer: 200000,
        timerProgressBar: true,
        allowOutsideClick: false,
        didOpen: () => {
          Swal.showLoading()
        },
      })
	}
</script>
```


