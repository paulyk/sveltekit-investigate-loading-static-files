<script context="module" lang="ts">
import { page } from "$app/stores";


    export async function load({fetch, page }) {
        
        console.log('content', page)

        const content = await fetch('/posts/first.md').then(resp => resp.text())
        console.log('content', content)

        return {
            props: {
                content
            }
        }
    }
</script>
<script lang="ts">
    export let content
</script>

<h1>Slug</h1>
{content}