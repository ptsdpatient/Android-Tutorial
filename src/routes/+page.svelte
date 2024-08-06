<script>
    import {onMount} from 'svelte'
    import Prism from 'prismjs';
    import ThreeScene from '../lib/ThreeScene.svelte';
    import 'prismjs/components/prism-javascript'; 
    import 'prismjs/components/prism-xml-doc';
    import 'prismjs/components/prism-java.js'; 
    

    import './prism-dark.css'
    import {Data} from "../lib/data"
    onMount(() => {
        Prism.highlightAll();
    });
</script>


<ThreeScene></ThreeScene> 

<!-- Header -->

<div class="p-3 h-screen w-1/4 flex flex-col fixed">
    <div class="rounded-lg text-white bg-gray-900 bg-opacity-80 overflow-y-auto overflow-x-auto">
        <button class="group flex flex-row justify-between w-full bg-black opacity-80 text-left px-3 py-2 rounded-lg">
            <div>
                Tanishq
            </div>
            <div class="transform mx-1 rotate-0 group-hover:-rotate-180 transition-all duration-300">
                ⌵
            </div>
        </button>
    </div>
</div>

<div class="w-11/12 md:w-3/4 flex flex-col ml-auto">
    {#each Data as data}
        <div class="w-3/4 backdrop-blur-sm bg-gray-900 bg-opacity-80 rounded-xl my-3  mx-auto flex  flex-col shadow-xl justify-around " >
            <div class="flex flex-row justify-between rounded-xl bg-black bg-opacity-30  py-1 px-1">
                <div></div>
                <button class="text-gray-200 tet-xl transform hover:bg-gray-600 hover:bg-opacity-50 hover:text-white py-1 px-3 rounded-lg transition-all duration-100 ease-in">copy 📄</button>
            </div>

            <div class="p-3">
                <pre class="whitespace-nowrap" style=""><code class="language-js text-base" >{data.code}</code></pre>
            </div>
        </div>
    {/each}
</div>
