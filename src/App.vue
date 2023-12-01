<template>
	<header>
		<h1>ระบบจัดการข้อมูลพนักงาน</h1>
	</header>
	<FormComponent @save="insertEmployee" />
	<section class="employee-content" v-if="employees.length > 0">
		<h2>ข้อมูลพนักงาน</h2>
		<ListData :employees="employees" />
	</section>
</template>

<script>
import FormComponent from "./components/FormComponent.vue";
import ListData from "./components/ListData.vue";

export default {
	name: "App",
	components: {
		ListData,
		FormComponent,
	},
	data() {
		return {
			employees: [],
		};
	},
	methods: {
		insertEmployee(data) {
			// console.log("รับข้อมูล ", data);
			this.employees.push(data);
		},
	},
};
</script>

<style>
* {
	box-sizing: border-box;
	margin: 0;
	padding: 0;
}

header {
	box-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
	margin: 2rem;
	padding: 1rem 2rem;
	border-radius: 1rem;
	background-color: palevioletred;
	color: #fff;
	text-align: center;
}

.employee-content {
	box-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
	margin: 2rem;
	padding: 1rem 2rem;
	border-radius: 1rem;
	text-align: center;
}

.employee-content h2 {
	font-size: 2rem;
	border-bottom: 4px solid #ccc;
	margin-bottom: 1rem;
}
</style>
