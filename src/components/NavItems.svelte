<script>
    import { navItems } from '../stores/store'
</script>

<ul>
    {#each $navItems as {text, path}}
      <li><a href={path}>{text}</a></li>
    {/each}
</ul>