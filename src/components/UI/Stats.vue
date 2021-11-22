<template>
<div class="wrapper-person view-sm">
  <div class="card-stats">
    <div class="one-third">
      <div class="stat-value">
        <slot name="statBody"></slot>
      </div>
      <div class="stat">
        <slot name="statFooter"> </slot>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  
}
</script>

