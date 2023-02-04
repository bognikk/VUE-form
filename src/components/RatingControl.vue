<template>
	<ul>
		<li :class="{ active: modelValue === 'poor' }">
			<button type="button" @click="activate('poor')">Poor</button>
		</li>
		<li :class="{ active: modelValue === 'average' }">
			<button type="button" @click="activate('average')">Average</button>
		</li>
		<li :class="{ active: modelValue === 'great' }">
			<button type="button" @click="activate('great')">Great</button>
		</li>
	</ul>
</template>

<script>
export default {
	props: ['modelValue'],
	emits: ['update:modelValue'],
	// data() {
	//   return {
	//     activeOption: this.modelValue,
	//   };
	// },
	// computed: {
	//   activeOption() {
	//     return this.modelValue;
	//   }
	// },
	methods: {
		activate(option) {
			this.$emit('update:modelValue', option);
		},
	},
};
</script>

<style lang="scss" scoped>
.active {
	border-color: #a00078;

	button {
		color: #a00078;
	}
}
ul {
	display: flex;
	padding: 0;
	margin: 0.5rem 0;
	list-style: none;

	li {
		display: flex;
		justify-content: center;
		align-items: center;
		margin: 0 1rem;
		border: 1px solid #ccc;

		button {
			padding: 1rem;
			font: inherit;
			border: none;
			background-color: transparent;
			cursor: pointer;
		}
	}
}
</style>