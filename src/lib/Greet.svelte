<script>
  import { invoke } from '@tauri-apps/api/tauri'

  let name = ''
  let greetMsg = ''

  async function greet() {
    greetMsg = await invoke('greet', { name })
  }
</script>

<div>
  <input id="greet-input" placeholder="Inserisci un animale..." bind:value="{name}" />
  <button on:click="{greet}">Genera</button>
  <p>{greetMsg}</p>
</div>
