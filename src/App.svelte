<script lang="ts">
  type Person = { name: string }

  let p: Person | undefined = $state(undefined)

  $effect(() => {
    // load person
    setTimeout(() => {
      p = { name: "bob" }
    }, 1000);
  });

  let displayName = $derived(p?.name ?? "anon")
</script>
<div>{ displayName }</div>
