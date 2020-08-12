<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body quote">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
</script>

<style>
.panel-body {
  font-family: "Amatic SC", cursive;
  font-size: 24;
  color: #1c1c1f;
  min-height: 200px;
}

.quote {
  cursor: pointer;
}

.quote:hover {
  background-color: rgb(236, 87, 87);
}
</style>