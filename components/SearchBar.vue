<script setup>
defineProps({ modelValue: String });
defineEmits(["update:modelValue", "search"]);
</script>

<template>
  <div style="margin-bottom: 1rem;">
    <input
      type="text"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
      placeholder="Search blogs..."
      style="padding: 0.5rem; border: 1px solid #ccc; border-radius: 4px;"
    />
    <button
      @click="$emit('search')"
    >
      Search
    </button>
  </div>
</template>

<style scoped>
  input:hover{
    background-color: rgba(190, 237, 249, 0.81);
  }
  
  input{
    color: rgb(5, 40, 73);
  }

  button{
    margin-left: 0.5rem;
    padding: 0.5rem 1rem; 
    background: #0070f3; 
    color: white; 
    border-radius: 4px;
  }

  button:hover{
    background-color:  #125cb1;
  }

  button:active{
    background-color:  #042c5b;
  }

</style>>
