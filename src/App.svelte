<script lang="ts">
  import { onMount } from "svelte";
  const dataSrc = "https://511on.ca/api/v3/get/roadconditions/";
  let conditionData: undefined | any = $state(undefined);
  let svgMap: any;

  onMount(async () => {
    try {
      const response = await fetch(dataSrc, {
        mode: "cors"
      });
      if (!response.ok) {
        throw new Error(`Response status: ${response.status}`);
      }
      conditionData = JSON.parse(await response.text());
      console.log(conditionData)
    } catch (err) {
      console.error(err);
    }
  })
</script>

<main>
  <section>
test!!
  </section>
</main>

<style>
  main {
    width: 100%;
    height: 100%;
    display: grid;
  }
</style>