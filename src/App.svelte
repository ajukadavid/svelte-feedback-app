<script>
	import FeedbackForm from "./components/FeedbackForm.svelte";
	import FeedbackList from "./components/FeedbackList.svelte";
	import FeedbackStats from "./components/FeedbackStats.svelte";

	let feedback = [
		{
			id: 1,
			rating: 10,
			text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae, culpa natus? Est odit dolor eum accusantium quibusdam omnis laborum quaerat? Quasi dolor quo nulla id, neque explicabo odio ut exercitationem. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae, culpa natus? Est odit dolor eum accusantium quibusdam omnis laborum quaerat? Quasi dolor quo nulla id, neque explicabo odio ut exercitationem. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae, culpa natus? Est odit dolor eum accusantium quibusdam omnis laborum quaerat? Quasi dolor quo nulla id, neque explicabo odio ut exercitationem.",
		},
		{
			id: 2,
			rating: 9,
			text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae, culpa natus? Est odit dolor eum accusantium quibusdam omnis laborum quaerat? Quasi dolor quo nulla id, neque explicabo odio ut exercitationem. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae, culpa natus? Est odit dolor eum accusantium quibusdam omnis laborum quaerat? Quasi dolor quo nulla id, neque explicabo odio ut exercitationem. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae, culpa natus? Est odit dolor eum accusantium quibusdam omnis laborum quaerat? Quasi dolor quo nulla id, neque explicabo odio ut exercitationem.",
		},
		{
			id: 3,
			rating: 8,
			text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae, culpa natus? Est odit dolor eum accusantium quibusdam omnis laborum quaerat? Quasi dolor quo nulla id, neque explicabo odio ut exercitationem. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae, culpa natus? Est odit dolor eum accusantium quibusdam omnis laborum quaerat? Quasi dolor quo nulla id, neque explicabo odio ut exercitationem. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae, culpa natus? Est odit dolor eum accusantium quibusdam omnis laborum quaerat? Quasi dolor quo nulla id, neque explicabo odio ut exercitationem.",
		},
	];

	$: count = feedback.length;
	$: average =
		feedback.reduce((a, { rating }) => a + rating, 0) / feedback.length;

	const addFeedback = (e) => {
		const newFeedback = e.detail

		feedback = [newFeedback, ...feed]
	};


	const deleteFeedback = (e) => {
		const itemId = e.detail;
		feedback = feedback.filter((item) => item.id != itemId);
	};
</script>

<main class="container">
	<FeedbackForm on:add-feedback={addFeedback} />

	<FeedbackStats {count} {average} />

	<FeedbackList {feedback} on:delete-feedback={deleteFeedback} />
</main>

<style>
</style>
