<script lang="ts">
	import Button from '$components/button/button.svelte';
	import ClickToCall from '$lib/common/other/ClickToCall.svelte';
	import HeadingAccent from '$lib/common/other/HeadingAccent.svelte';
	import FaqSection from '$lib/common/sections/FaqSection.svelte';
	import TemplateTestimonialSection from '$lib/common/sections/TemplateTestimonialSection.svelte';
	import { rootRoutes } from '$lib/seo/routes';
	import ThreeBars from '$lib/common/other/ThreeBars.svelte';

	const whatWeHandle = [
		{
			title: 'Repair, all brands',
			description:
				'Every major make and model. Compressors, capacitors, fan motors, refrigerant leaks, electrical faults.'
		},
		{
			title: 'Repair vs. replace',
			description: "If a repair doesn't make financial sense, we'll say so, with numbers."
		},
		{
			title: 'Heatings side included',
			description: 'Heat strips and heat pump heating repaired along with the cooling side.'
		},
		{
			title: 'Same process, every time',
			description:
				'You call. We show up in the window we gave you. We quote first. We fix it right.'
		}
	];

	//section 4 data - FAQ
	const faqs = [
		{
			question: 'How fast can you get here?',
			answer:
				'Scheduled repairs get a real time window, not a four-hour range. For emergencies, we aim to be at your door within the hour, 24/7.'
		},
		{
			question: 'Do you repair all A/C brands?',
			answer: 'Yes. Every major make and model, whether we installed it or not.'
		},
		{
			question: 'Should I repair or replace?',
			answer:
				"We'll tell you straight. If the repair cost approaches the value of the remaining system life, we'll show you the numbers for both and let you decide."
		}
	];
</script>

<!-- ========= Section 1 * Hero =================== -->
<section class="flex flex-col gap-6 p-y">
	<HeadingAccent>Air · Repair</HeadingAccent>
	<h1 class="hero-heading [&_span]:text-primary-700">
		Broken A/C.<br />
		<span>Fixed properly.</span>
	</h1>

	<div class="grid gap-6 lg:grid-cols-[2fr_1fr]">
		<p class="max-200 text-xl text-foreground/75 lg:text-2xl">
			Every major brand. A straight diagnosis, a quote before we start, and a repair that holds.
		</p>

		<div class="grid place-items-center gap-4 *:w-full sm:grid-cols-2">
			<Button class="sm:h-16" href={rootRoutes.contact.href}>Book a Visit</Button>
			<ClickToCall variant="underline-dark" />
		</div>
	</div>
</section>

<!-- ========= Section 2 * What We Handle =================== -->
<section class="max-w-200 text-lg leading-relaxed text-foreground/80 lg:text-xl">
	<p class="max-w-200 text-lg leading-relaxed text-foreground/80 lg:text-xl">
		An A/C failure in Central Florida is not an inconvenience. It's a clock. We diagnose in plain
		language, tell you what it costs before we touch anything, and give you an honest answer
		onwhether repairing makes more sense than replacing. If your system heats as well as cools,
		service that side too.
	</p>
</section>

<!-- ════════════ SECTION 3 * WHAT WE HANDLE ════════════ -->
<section class="flex flex-col gap-6 p-y lg:gap-12">
	<span class="font-display text-xs font-semibold tracking-widest text-foreground/50 uppercase lg:text-sm">
		What we handle
	</span>

	<ul class="grid border-t border-l border-border/20 sm:grid-cols-2">
		{#each whatWeHandle as item (item.title)}
			<li class="flex gap-4 border-r border-b border-border/20 p-6 lg:p-8">
				<ThreeBars class="mt-1.5 shrink-0" scale="sm" size="2rem" color="primary" />

				<div class="flex flex-col gap-2.5">
					<h3 class="font-display text-2xl font-black uppercase lg:text-3xl">{item.title}</h3>
					<p class="leading-relaxed text-foreground/70">{item.description}</p>
				</div>
			</li>
		{/each}
	</ul>
</section>


<!-- ========= Section 4 * FAQ =================== -->
 <FaqSection {faqs}>
    {#snippet heading()}
        A/C repair <span>questions.</span>
        {/snippet}
 </FaqSection>

 <!-- ========= Section 5 * Testimonials =================== -->
<!--TODO: Swap before launch, ask Mitch later-->
<TemplateTestimonialSection author={{ name: 'Colleen A.',abbr: 'CA'}}>
        Came out on a Christmas emergency. Lost power to our oven. Fixed in no time. <span>10/10.</span>
</TemplateTestimonialSection>

<!-- ========= Section 6 * Call to Action =================== -->
<section
    class="full-bg flex flex-col items-center gap-6 p-y text-center before:border-t before:border-border/20"
    >
    <h2 class="text-3xl xs:text-4xl lg:text-5xl">Get it fixed.</h2>
    <p class="max-w-100. text-lg text-foreground/75 lg:text-xl">
        Call or book a visit. Diagnosis in plain language, quote before we start.
    </p>
    <Button href={rootRoutes.contact.href} class="met-3 w-full max-w-50 sm:w-fit">Book a Visit</Button>
    </section>

<style>
    .hero-heading {
        font-size: clamp(2rem, 8vw, 8rem);
        line-height:0.9;
    }
</style>
