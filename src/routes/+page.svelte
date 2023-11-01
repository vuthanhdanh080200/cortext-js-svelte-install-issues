<script lang="ts">
  import { ComputeEngine } from "@cortex-js/compute-engine";
  const ce = new ComputeEngine();
  ce.parse("f\\left(x\\right)\\coloneq3x").evaluate();
  ce.parse("a:=3").evaluate();
  const expr = ce.parse("f(3)");
  const fn = expr.compile("javascript", {
    optimize: ["evaluate"],
  });
  const eva = expr.evaluate().valueOf();
  console.info((fn as any)({}));
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>
