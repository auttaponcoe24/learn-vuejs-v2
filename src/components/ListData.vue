<template>
	<ul>
		<Person
			v-for="(item, index) in employees"
			:key="index"
			:name="item.name"
			:salary="item.salary"
			:department="item.department"
		/>
	</ul>
</template>

<script>
import Person from "./Person.vue";

export default {
	name: "ListData",
	components: {
		Person,
	},
	props: ["employees"],
	// data() {
	// 	return {
	// 		employees: [
	// 			{
	// 				id: 1,
	// 				name: "ก้อง",
	// 				salary: 30000,
	// 				department: "programmer",
	// 				isVisible: false,
	// 			},
	// 			{
	// 				id: 2,
	// 				name: "แก้ม",
	// 				salary: 35000,
	// 				department: "sell",
	// 				isVisible: false,
	// 			},
	// 			{
	// 				id: 3,
	// 				name: "โจโจ้",
	// 				salary: 40000,
	// 				department: "graphic design",
	// 				isVisible: false,
	// 			},
	// 			{ id: 4, name: "Joe", department: "fff", isVisible: false },
	// 		],
	// 	};
	// },
	// methods: {
	// 	toggleVisible(id) {
	// 		// console.log("child ID  = ", id);
	// 		this.employees = this.employees.map((item) => {
	// 			if (item.id === id) {
	// 				return { ...item, isVisible: !item.isVisible };
	// 			}
	// 			return item;
	// 		});
	// 	},
	// 	deleteEmp(id) {
	// 		// console.log("child ID = ", id);
	// 		this.employees = this.employees.filter((item) => item.id !== id);
	// 	},
	// },
};
</script>

<style scoped>
ul {
	list-style: none;
	margin: 1rem 0;
	padding: 0;
	display: flex;
	flex-direction: column;
}
</style>
