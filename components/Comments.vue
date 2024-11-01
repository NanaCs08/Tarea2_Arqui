<template>
    <div id="comments-section" class="comments-section"></div>
  </template>
  
  <script setup>
  import { onMounted, onUnmounted } from 'vue'
  
  onMounted(() => {
    // Eliminar cualquier script de Utterances existente para evitar duplicados
    const existingScript = document.getElementById('comments-script')
    if (existingScript) existingScript.remove()
  
    // Crear un nuevo script de Utterances
    const script = document.createElement('script')
    script.src = "https://utteranc.es/client.js"
    script.id = 'comments-script' // Asignar un ID único al script
    script.setAttribute('repo', "NanaCs08/Tarea2_Arqui")
    script.setAttribute('issue-term', "pathname")
    script.setAttribute('theme', "github-dark")
    script.setAttribute('crossorigin', "anonymous")
    script.async = true
    document.getElementById('comments-section').appendChild(script)
  })
  
  onUnmounted(() => {
    // Eliminar el script de Utterances al desmontar el componente
    const script = document.getElementById('comments-script')
    if (script) script.remove()
  })
  </script>
  
  <style scoped>
  .comments-section {
    margin-top: 2rem;
  }
  </style>
  