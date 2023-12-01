<template>
	<form @submit="submitForm">
		<div class="form-control">
			<label for="emp-name">ชื่อพนักงาน : </label>
			<input type="text" v-model.trim="employee.name" />
		</div>
		<div class="form-control">
			<label for="salary">เงินเดือน : </label>
			<input type="number" v-model="employee.salary" />
		</div>
		<div class="form-control">
			<label for="department">ตำแหน่งงาน : </label>
			<select name="" id="" v-model="employee.department">
				<option value="ฝ่ายการเงิน">ฝ่ายการเงิน</option>
				<option value="ฝ่ายการตลาด">ฝ่ายการตลาด</option>
				<option value="ฝ่ายขาย">ฝ่ายขาย</option>
			</select>
		</div>
		<div class="form-control">
			<h2>เพศ :</h2>
			<div>
				<input type="radio" value="ชาย" v-model="employee.gender" />
				<label for="ชาย">ชาย</label>
			</div>
			<div>
				<input type="radio" value="หญิง" v-model="employee.gender" />
				<label for="หญิง">หญิง</label>
			</div>
		</div>
		<div class="form-control">
			<h2>ทักษะด้านภาษา :</h2>
			<div>
				<input type="checkbox" value="ภาษาอังกฤษ" v-model="employee.skill" />
				<label for="ภาษาอังกฤษ">ภาษาอังกฤษ</label>
			</div>
			<div>
				<input type="checkbox" value="ภาษาญี่ปุ่น" v-model="employee.skill" />
				<label for="ภาษาญี่ปุ่น">ภาษาญี่ปุ่น</label>
			</div>
		</div>
		<div>
			<button type="submit">บันทึกข้อมูล</button>
		</div>
		<!-- {{ JSON.stringify(employee) }} -->
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
				department: "ฝ่ายการเงิน",
				gender: "",
				skill: [],
			},
		};
	},
	methods: {
		submitForm(e) {
			e.preventDefault();
			const newEmployee = {
				name: this.employee.name,
				salary: this.employee.salary,
				department: this.employee.department,
				gender: this.employee.gender,
				skill: this.employee.skill,
			};
			this.$emit("save", newEmployee);
			this.resetForm();
		},
		resetForm() {
			this.employee.name = "";
			this.employee.salary = 0;
			this.employee.department = "ผ่านการตลาด";
			this.employee.gender = "";
			this.employee.skill = [];
		},
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

input,
select {
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

input[type="radio"],
input[type="checkbox"] {
	display: inline-block;
	width: auto;
	margin-left: 1rem;
}
input[type="radio"] + label,
input[type="checkbox"] + label {
	font-weight: bold;
	padding: 1rem;
}
h2 {
	font-size: 1rem;
	margin: 0.5rem 0;
}
</style>
