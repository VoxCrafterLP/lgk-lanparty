<script lang="ts">
    import "../app.css";
    import {particlesInit} from '@tsparticles/svelte';
    import {loadSlim} from '@tsparticles/slim';
    import {onMount} from "svelte";

    let ParticlesComponent: any;

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
        id="tsparticles"
        class="fixed top-0 left-0 w-full h-full -z-10"
        options="{particlesConfig}"/>
<img src="/lgk.png" alt="LGK Logo" class="absolute top-4 left-4 w-24 invisible xl:visible"/>
<slot/>
