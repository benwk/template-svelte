<script lang="ts">
	import { DashboardPage, ExamplesNav } from '@/components';
	import * as PageHeader from '@/components/page-header';
	import { Icons } from '@/components/icons';
	import { buttonVariants } from '$lib/components/ui/button';
	import { Separator } from '$lib/components/ui/separator';
	import { siteConfig } from '$lib/config/site';
	import { cn } from '@/utils';
	import { ChevronRight } from 'radix-icons-svelte';
</script>

<div class="container relative pb-10">
	<!-- <StyleSwitcher /> -->
	<PageHeader.Root>
		<a
			class="inline-flex items-center rounded-lg bg-muted px-3 py-1 text-sm font-medium"
			href="https://benwk.com"
		>
			🎉<Separator class="mx-2 h-4" orientation="vertical" /> Ben's Coding, now in preview!
			<ChevronRight class="ml-1 h-4 w-4" />
		</a>
		<PageHeader.Heading>Ben's Coding</PageHeader.Heading>
		<PageHeader.Description>
			Programming is my language, cmd + c and cmd + v are my lifeblood.
		</PageHeader.Description>
		<p class="text-sm text-orange-700 dark:text-orange-400">
			Follow me at <a
				href={siteConfig.links.benGithub}
				target="_blank"
				rel="noreferrer"
				class="font-medium underline underline-offset-4">benwk</a
			>
			on GitHub , and
			<a
				href={siteConfig.links.benTwitter}
				target="_blank"
				rel="noreferrer"
				class="font-medium underline underline-offset-4">@benwkz</a
			> on twitter.
		</p>
		<div class="flex w-full items-center space-x-4 pb-8 pt-4 md:pb-10">
			<a href="/docs" class={cn(buttonVariants())}> Get Started </a>
			<a
				target="_blank"
				rel="noreferrer"
				href={siteConfig.links.github}
				class={cn(buttonVariants({ variant: 'outline' }))}
			>
				<Icons.gitHub class="mr-2 h-4 w-4" />
				GitHub
			</a>
		</div>
	</PageHeader.Root>
	<ExamplesNav class="[&>a:first-child]:text-primary" />
	<section
		class="space-y-8 overflow-hidden rounded-lg border-2 border-primary dark:border-muted md:hidden"
	>
		<img
			src="/examples/dashboard-light.png"
			width={1280}
			height={866}
			alt="Dashboard"
			class="block dark:hidden"
		/>
		<img
			src="/examples/dashboard-dark.png"
			width={1280}
			height={866}
			alt="Dashboard"
			class="hidden dark:block"
		/>
	</section>
	<section class="hidden md:block">
		<div class="overflow-hidden rounded-lg border bg-background shadow-xl">
			<DashboardPage />
		</div>
	</section>
</div>
