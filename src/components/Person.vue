<template>
	<ul>
		<li>
			<h1>ชื่อ : {{ name }}</h1>
			<button @click="showDescription(id)">ดูรายละเอียด</button>&nbsp;
			<button>ลบข้อมูล</button>
			<div v-show="isVisible">
				<p>เงินเดือน : {{ salary }}, ตำแหน่งงาน : {{ department }}</p>
			</div>
		</li>
	</ul>
</template>
<script>
export default {
	name: "Person",
	data() {
		return {};
	},
	props: {
		id: {
			type: Number,
		},
		name: {
			type: String,
			required: true,
		},
		salary: {
			type: Number,
			required: true,
			default: 25000,
		},
		department: {
			type: String,
			required: true,
		},
		isVisible: {
			type: Boolean,
		},
	},
	methods: {
		showDescription(id) {
			// console.log(id);
			this.$emit("show", id);
		},
	},
	// props: {
	// 	name,
	// },
};
</script>
<style scoped>
li {
	margin: 1rem 0;
	font-size: 1rem;
	font-weight: bold;
	background-color: #8ddba4;
	padding: 0.5rem;
	color: #1f1f1f;
	border-radius: 1rem;
}

button {
	font-size: inherit;
	cursor: pointer;
	border: 1px solid #ff0077;
	background-color: #ff0077;
	color: #fff;
	padding: 2px 1rem;
	border-radius: 1rem;
	box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
}
</style>
