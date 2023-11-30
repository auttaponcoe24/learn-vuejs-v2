<template lang="">
	<li>
		<img src="https://cdn-icons-png.flaticon.com/256/924/924915.png" alt="" />
		<hr />
		<slot></slot>
	</li>
</template>

<script>
export default {
	name: "Card",
};
</script>

<style scoped>
li {
	margin: 1rem 0;
	font-size: 1rem;
	font-weight: bold;
	background-color: purple;
	padding: 1rem;
	color: #ffffff;
	border-radius: 1rem;
	display: flex;
	flex-direction: column;
	align-items: center;
	gap: 0.2rem;
}

hr {
	width: 100%;
}

img {
	width: 100px;
	height: 100px;
}
</style>
