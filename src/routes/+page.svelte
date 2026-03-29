<script lang="ts">
import Header from '$lib/components/layout/Header.svelte';
import Profile from '$lib/components/ui/Profile.svelte';
import Experience from '$lib/components/ui/Experience.svelte';
import Tag from '$lib/components/ui/Tag.svelte';
import Section from '$lib/components/ui/Section.svelte';
import resumeData from '$lib/data/resume.json';
import type { ResumeData } from '$lib/types/resume.types';
import Project from '$lib/components/ui/Project.svelte';
import Education from '$lib/components/ui/Education.svelte';
import Certificate from '$lib/components/ui/Certificate.svelte';
import Footer from '$lib/components/layout/Footer.svelte';

let resume = resumeData as ResumeData;
</script>

<div class="min-h-screen bg-(--bg) text-(--sub-title) font-sans antialiased whitespace-pre-line">
	<Header />
	<div class="px-6 py-16 md:max-w-4xl md:mx-auto md:px-0">
		<Profile {...resume} />
		<Section title="Experience">
			<div class="space-y-8">
				{#each resume.experiences as exp (exp.id)}
					<Experience {...exp} />
				{/each}
			</div>
		</Section>
		<Section title="Project">
			<div class="space-y-8">
				{#each resume.projects as prj (prj.id)}
					<Project {...prj} />
				{/each}
			</div>
		</Section>
		<Section title="Skills">
			<div class="flex flex-wrap gap-2">
				{#each resume.skills as skill (skill)}
					<Tag>{skill}</Tag>
				{/each}
			</div>
		</Section>
		<Section title="Education">
			<div class="flex flex-wrap gap-2">
				{#each resume.educations as edu (edu.id)}
					<Education {...edu} />
				{/each}
			</div>
		</Section>
		<Section title="Certificate">
			<div class="flex flex-wrap gap-2">
				{#each resume.certificates as cer (cer.id)}
					<Certificate {...cer} />
				{/each}
			</div>
		</Section>
	</div>
	<Footer />
</div>