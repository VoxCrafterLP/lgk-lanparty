<script lang="ts">
    import "../app.css";
    import {particlesInit} from '@tsparticles/svelte';
    import {loadSlim} from '@tsparticles/slim';
    import {onMount} from "svelte";

    let ParticlesComponent: any;
    let showParticles: boolean = false;

    onMount(async () => {
        const module = await import('@tsparticles/svelte');
        ParticlesComponent = module.default;
    });

    let particlesConfig = {
        particles: {
            color: {
                value: '#ffffff'
            },
            links: {
                enable: true,
                color: '#ffffff'
            },
            move: {
                enable: true,
            },
            number: {
                value: 60
            }
        }
    };

    void particlesInit(async (engine) => {
        await loadSlim(engine);
    });
</script>

<svelte:component
        this="{ParticlesComponent}"
        id="bg-particles"
        class="fixed top-0 left-0 w-full h-full -z-10 duration-[2000ms] transition-all"
        options="{particlesConfig}"
        style={'opacity: ' + (showParticles ? 100 : 0) + ';'}
        on:particlesLoaded="{() => showParticles = true}"
/>
<img src="/lgk.png" alt="LGK Logo" class="absolute top-4 left-4 w-24 invisible xl:visible"/>
<slot/>
