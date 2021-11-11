<script context="module" lang="ts">
    export async function load({ fetch }) {
        console.log('load post')

        
        const test = await fetch('/api/first.json').then(r => r.text())

        console.log('load post', test)

        return {
            props: {
                content: test
            }
        }
    }
</script>

<script lang="ts">
    export let content = ""
</script>

<h1>Post</h1>

{JSON.stringify(content, null, 2)}

