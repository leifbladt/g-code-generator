<template>
    <div class="hello">
        <h1>G-Code Generator</h1>
        <p>
            <button v-on:click="generate">Generate</button><br>
            <textarea v-model="message" placeholder="add multiple lines"></textarea>

        </p>
    </div>
</template>

<script>

export default {
  name: 'GCodeGenerator',
  props: {
      message: String
  },
  methods: {
      generate: generate
  }
}

function generate() {
    this.message = `G0 Z10; Z at 10 mm

M201 X750 Y750; acceleration

M400; complete all moves in the planner
G1 F3600

G1 X25 Y25
G1 X175 Y25
G1 X175 Y175
G1 X25 Y175
G1 X25 Y25`;
}
</script>
