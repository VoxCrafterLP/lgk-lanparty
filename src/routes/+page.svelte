<script lang="ts">
    export let data;
</script>

<div class="hero min-h-screen">
    <div class="hero-content text-center">
        <div class="flex flex-col xl:flex-row justify-between w-[80vw] gap-8 xl:gap-0">
            <div class="card xl:w-[40rem] bg-base-300 shadow-xl">
                <div class="card-body flex flex-col items-center gap-6">
                    <h1 class="card-title text-6xl font-extrabold text-transparent bg-clip-text bg-gradient-to-r from-pink-500 to-blue-600">
                        Lan-Party!
                    </h1>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam maximus justo sit amet ipsum
                        varius
                        ullamcorper. Proin mattis mattis viverra. Etiam tristique ligula nulla, sodales vestibulum
                        purus
                        volutpat ac. Cras vitae metus at velit porttitor aliquam at non neque. In quam mauris,
                        aliquet eget
                        pretium vitae, condimentum ac est. Duis rutrum vel est venenatis imperdiet. Mauris augue
                        nisi, porttitor
                        id ligula vel, accumsan cursus est. Aliquam nunc tellus, molestie et luctus suscipit,
                        porttitor id nisi.
                        Ut id tempus risus. Ut quis arcu quis elit pulvinar mollis eu ut turpis. Maecenas ac euismod
                        quam. Nunc
                        eleifend purus convallis lorem egestas dapibus. Nullam consequat arcu in nibh pellentesque
                        imperdiet.
                        Praesent non nisl sed dui semper faucibus. Suspendisse potenti. Mauris nec malesuada
                        augue. </p>
                </div>
            </div>
            <div class="card flex flex-col justify-center items-center gap-14 bg-base-300 p-12 xl:w-[28rem]">
                <h2 class="text-4xl text-base-content font-bold">22 März 2024</h2>
                <div class="stats shadow stats-vertical lg:stats-horizontal">
                    <div class="stat">
                        <div class="stat-title text-xl">Fräi Plaazen</div>
                        <div class="stat-value text-6xl"
                             class:text-green-500={data.slots >= 50}
                             class:text-red-500={data.slots < 50}
                        >
                            {data.slots}
                        </div>
                    </div>
                    <div class="stat">
                        <div class="stat-title text-xl">Participanten</div>
                        <div class="stat-value text-6xl">
                            {data.participants}
                        </div>
                    </div>
                </div>
                <a href={data.slots === 0 ? '' : '/register'}>
                    <button class="btn btn-primary btn-lg w-48 hover:scale-110 hover:btn-accent transition-all"
                            class:btn-disabled={data.slots === 0}>
                        Umällen
                    </button>
                </a>
            </div>
        </div>
    </div>
</div>
