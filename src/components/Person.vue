<template>
	<Card>
		<h1>ชื่อ : {{ name }}</h1>
		<div>
			<button @click="showDescription(id)">ดูรายละเอียด</button>&nbsp;
			<button @click="deleteEmployee(id)">ลบข้อมูล</button>
		</div>
		<transition name="fade">
			<div v-show="isVisible">
				<p>เงินเดือน : {{ salary }}, ตำแหน่งงาน : {{ department }}</p>
			</div>
		</transition>
	</Card>
</template>
<script>
import Card from "./Card.vue";

export default {
	name: "Person",
	components: {
		Card,
	},
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
		deleteEmployee(id) {
			// console.log("delte id", id);
			this.$emit("delete", id);
		},
	},
};
</script>
<style scoped>
/* li {
	margin: 1rem 0;
	font-size: 1rem;
	font-weight: bold;
	background-color: #8ddba4;
	padding: 0.5rem;
	color: #1f1f1f;
	border-radius: 1rem;
} */

h1 {
}

button {
	font-size: inherit;
	cursor: pointer;
	border: 1px solid #ff0077;
	background-color: #ff0077;
	color: #fff;
	padding: 0.2rem 1rem;
	border-radius: 0.4rem;
	box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
}

.fade-enter-from {
	opacity: 0;
}
.fade-enter-active {
	transition: all 0.5s linear;
}
</style>
