<template>
  <li>
    <a href="javascript:void(0);">
      {{ name }}
    </a>
  </li>
</template>

<script>
  export default {
    props : {
      name : {
        type : String,
        default : ""
      }
    }
  }
</script>