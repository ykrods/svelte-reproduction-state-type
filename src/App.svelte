<script lang="ts">
  type Person = { name: string }

  let p: Person | undefined = $state(undefined)

  /**
   * let p = $state(undefined as (Person | undefined));
   * let p = $state<Person | undefined>(undefined);
   * let p: Person | undefined = $state()
   */

  $effect(() => {
    // load person
    setTimeout(() => {
      p = { name: "bob" }
    }, 1000);
  });

  $effect(() => {
    console.log(p?.name);
  });

  let displayName = $derived(p?.name ?? "anon")
  // let displayName = $derived.by(() => p?.name ?? "anon")
</script>
<div>{ displayName }</div>
