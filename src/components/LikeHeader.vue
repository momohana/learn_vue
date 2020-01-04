<template>
  <div>
    <slot name="title" :user="user" text="text"></slot>
    <h2>いいねの数</h2>
    <slot name="number"></slot>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        firstName: "Jack",
        lastName: "Donald"
      }
    };
  }
};
</script>
