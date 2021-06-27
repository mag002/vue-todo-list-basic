<template>
  <div class="d-flex item">
    <div class="icon">
      <img src="../assets/trash-alt-solid.svg" alt="" />
    </div>
    <div class="icon">
      <img src="../assets/check-solid.svg" alt="" />
    </div>
    <p>this is item</p>
  </div>
</template>

<script>
export default {
  name: "TodoListItem",
};
</script>

<style lang="scss" scoped>
.item {
  align-items: center;
  padding: 20px;
  .icon {
    padding: 7px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 100%;
    border: 1px solid #d2d2d2;
    margin-right: 20px;
    &:hover {
      background: lightskyblue;
      border-color: lightskyblue;
      img {
        filter: invert(1);
        opacity: 1;
      }
    }
    img {
      width: 18px;
      height: 18px;
      opacity: 0.5;
    }
  }
  p {
    font-size: 1.5em;
  }
}
</style>
