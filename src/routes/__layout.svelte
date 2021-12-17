<script>
    import '$lib/theme.css'
    import 'normalize.css'
    import Header from '$lib/Shell/Header.svelte'
    import MenuGrid from '$lib/Icons/MenuGrid.svelte';
</script>

<Header brand="ad" sticky>
    <div slot="menu"/>
</Header>
<slot/>