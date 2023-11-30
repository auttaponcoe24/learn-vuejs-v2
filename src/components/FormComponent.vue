<template>
	<form>
		<div class="form-control">
			<label for="emp-name">ชื่อพนักงาน : </label>
			<input type="text" v-model.trim="employee.name" />
		</div>
		<div class="form-control">
			<label for="emp-name">เงินเดือน : </label>
			<input type="number" v-model="employee.salary" />
		</div>
		<div>
			<button type="submit">บันทึกข้อมูล</button>
		</div>
		{{ JSON.stringify(employee) }}
	</form>
</template>

<script>
export default {
	name: "FormComponent",
	data() {
		return {
			employee: {
				name: "",
				salary: 0,
			},
		};
	},
};
</script>

<style scoped>
form {
	margin: 2rem auto;
	padding: 1rem;
	max-width: 40rem;
	border-radius: 12px;
	box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
	background-color: #fff;
}
.form-control {
	margin: 0.5rem 0;
}

label {
	font-weight: bold;
}

input {
	display: block;
	width: 100%;
	font: inherit;
	margin-top: 0.5rem;
	padding: 2px 4px;
}

button {
	font: inherit;
	background-color: purple;
	color: #fff;
	cursor: pointer;
	padding: 4px 6px;
	border: 1px solid purple;
	border-radius: 0.5rem;
	width: 100%;
}
</style>
