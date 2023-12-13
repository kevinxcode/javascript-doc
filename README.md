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


