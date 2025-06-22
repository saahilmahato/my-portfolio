<script lang="ts">
	import Section from '$lib/components/Section.svelte';
	import Headline from '$lib/components/Headline.svelte';
	import Subheadline from '$lib/components/Subheadline.svelte';

	let status = '';
	let submitting = false;

	const headlineText = 'Get in Touch';
	const subHeadlineText =
		'Have a question, collaboration idea, or just wanna say hi? Hit me up below.';

	async function handleSubmit(event: Event) {
		event.preventDefault();
		status = '';
		submitting = true;

		const form = event.target as HTMLFormElement;
		const data = new FormData(form);

		try {
			const response = await fetch(form.action, {
				method: form.method,
				body: data,
				headers: {
					Accept: 'application/json'
				}
			});

			if (response.ok) {
				status = 'Boom! Message delivered. Catch you on the flip side ✌️';
				form.reset();
			} else {
				status = "Nah fam, that didn't go through 🚫. Hit resend and let's vibe better!";
			}
		} catch {
			status = "Nah fam, that didn't go through 🚫. Hit resend and let's vibe better!";
		} finally {
			submitting = false;
		}
	}
</script>

<Section id="contact">
	<Headline text={headlineText} />
	<Subheadline text={subHeadlineText} />

	<form
		action="https://formspree.io/f/xovwngdy"
		method="POST"
		onsubmit={handleSubmit}
		class="mt-8 flex min-w-2/3 flex-col gap-5 rounded-2xl border-2 border-green-400 bg-gradient-to-br from-green-100/70 via-green-200/60 to-yellow-100/50 p-8 shadow-[0_4px_15px_rgba(72,187,120,0.35)]"
	>
		<input type="hidden" name="_subject" value="New contact message from portfolio site" />

		<input
			type="text"
			name="name"
			required
			placeholder="Your full name"
			class="focus:ring-opacity-60 rounded-lg border border-green-300 bg-green-50/80 px-4 py-3 text-green-900 placeholder-green-600 shadow-inner transition focus:ring-4 focus:ring-green-400 focus:outline-none"
			disabled={submitting}
		/>

		<input
			type="email"
			name="email"
			required
			placeholder="Your email"
			class="focus:ring-opacity-60 rounded-lg border border-green-300 bg-green-50/80 px-4 py-3 text-green-900 placeholder-green-600 shadow-inner transition focus:ring-4 focus:ring-green-400 focus:outline-none"
			disabled={submitting}
		/>

		<input
			type="text"
			name="institution"
			placeholder="Where you work or study"
			class="focus:ring-opacity-60 rounded-lg border border-green-300 bg-green-50/80 px-4 py-3 text-green-900 placeholder-green-600 shadow-inner transition focus:ring-4 focus:ring-green-400 focus:outline-none"
			disabled={submitting}
		/>

		<textarea
			name="message"
			required
			placeholder="Write your message here..."
			rows="5"
			class="focus:ring-opacity-60 resize-none rounded-lg border border-green-300 bg-green-50/80 px-4 py-3 text-green-900 placeholder-green-600 shadow-inner transition focus:ring-4 focus:ring-green-400 focus:outline-none"
			disabled={submitting}
		></textarea>

		<button
			type="submit"
			class="mt-6 cursor-pointer rounded-full bg-green-600 py-3 font-semibold text-white transition-colors duration-300 hover:bg-green-700 focus:ring-2 focus:ring-green-400 focus:ring-offset-1 focus:outline-none"
			disabled={submitting}
		>
			{submitting ? 'Sending...' : 'Send'}
		</button>

		{#if status}
			<p class="mt-3 font-medium text-green-900 italic drop-shadow-sm">{status}</p>
		{/if}
	</form>
</Section>
