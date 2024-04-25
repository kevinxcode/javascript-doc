```
<script>
function editQuestion(id,question,question_en,limit_data){
	$('#id').val(id);
	$('#question').val(question);
	$('#question_en').val(question_en);
	$('#limit_data').val(limit_data);
}
function delQuestion(id,token_question){
	if(confirm('are you sure to delete !')){
		const url = '<?php echo prefix_url;?>app/vo/delQuestion?id='+id+'&&token_question='+token_question; 
		fetch(url)
		.then(response => {
			if (!response.ok) {
				throw new Error('Network response was not ok.');
			}
			return response.json();
		})
		.then(data => {
			location.reload();
		})
		.catch(error => {
			console.error('Error fetching data:', error);
		});
	}
}
function saveQuestion() {
	var form = document.getElementById('myForm');
	var formData = new FormData(form);

	var values = {};
	// Loop through each form element
	formData.forEach(function(value, key) {
		values[key] = value;
	});

	var requestOptions = {
    	method: 'POST',
		headers: {
      		'Content-Type': 'application/json'
    	},
    	body: JSON.stringify(values)
	};
	var url = '<?php echo prefix_url;?>app/vo/addQuestion'; 

	fetch(url, requestOptions)
	.then(response => {
		if (!response.ok) {
		throw new Error('Network response was not ok.');
		}
		return response.json(); // Parse response body as JSON
	})
	.then(data => {
		console.log(data);
		// const obj = JSON.parse(data);
		if(data.i_err=='0'){
			location.reload();
		}else{
			alert(obj.msg);
		}
	})
	.catch(error => {
		console.log('Error submitting form:', error);
	});
}
function addAnswer(token_question,question_txt){
	$('#question_txt_view').show();
	$('#id_answer').val(0);
	$('#token_question').val(token_question);
	$('#question_txt').val(question_txt);
	$('#answer').val('');
	$('#answer_en').val('');
}
function editAnswer(id,token_question,answer,answer_en){
	$('#question_txt_view').hide();
	$('#id_answer').val(id);
	$('#token_question').val(token_question);
	$('#question_txt').val('');
	$('#answer').val(answer);
	$('#answer_en').val(answer_en);
}
function saveAnswer(){
	var form = document.getElementById('myForm_answer');
	var formData = new FormData(form);

	var values = {};
	// Loop through each form element
	formData.forEach(function(value, key) {
		values[key] = value;
	});
	
	var requestOptions = {
    	method: 'POST',
		headers: {
      		'Content-Type': 'application/json'
    	},
    	body: JSON.stringify(values)
	};
	var url = '<?php echo prefix_url;?>app/vo/addAnswer'; 

	fetch(url, requestOptions)
	.then(response => {
		if (!response.ok) {
		throw new Error('Network response was not ok.');
		}
		return response.json(); // Parse response body as JSON
	})
	.then(data => {
		console.log(data);
		if(data.i_err=='0'){
			location.reload();
		}else{
			alert(obj.msg);
		}
	})
	.catch(error => {
		console.log('Error submitting form:', error);
	});
}
function delAnswer(id){
	if(confirm('are you sure to delete !')){
		const url = '<?php echo prefix_url;?>app/vo/delAnswer?id='+id; 
		fetch(url)
		.then(response => {
			if (!response.ok) {
				throw new Error('Network response was not ok.');
			}
			return response.json();
		})
		.then(data => {
			location.reload();
		})
		.catch(error => {
			console.error('Error fetching data:', error);
		});
	}
}
</script>


```