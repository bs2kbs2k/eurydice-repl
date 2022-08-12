<script lang="ts">
  import icon from './assets/eurydice.svg';
  import evaluate from 'eurydice/src/evaluate';
  import parse from 'eurydice/src/parse';
  import printValue from 'eurydice/src/print';
  let expr = "...4d20";
  function evalString(expr: string): string {
    try {
      return printValue(evaluate(parse(expr)));
    } catch (e) {
      return e;
    }
  }
</script>

<main>
  <img src={icon} alt="Eurydice icon">
  <h1>Try Eurydice</h1>
  <input type="text" bind:value={expr} autocapitalize="none" autocomplete="none" autocorrect="none">
  <div>{evalString(expr)}</div>
</main>