<template>
  <button class="action-button rounded-xl my-5 lighter "> {{ title }}</button>
</template>

<script>
export default {
  props: ['title']
}
</script>


<style scoped>
.action-button {
  margin-left: auto;
  margin-right: auto;
  font-family: 'EFCOBrookshireRegular', sans-serif;
  padding: 1.5rem;
  width: 12rem;
  border-color: transparent;
  background-color: #92856A;
  transition: all .1s;
}

.action-button:hover {
  filter: brightness(130%);
  transform: scale(0.97);
}

.action-button:focus {
  filter: brightness(140%);
  transform: scale(0.93);
  border-color: transparent;
}

/* Medium devices (tablets, 768px and up)  */
@media (min-width: 640px) {
  .action-button {
    width: 10rem;
    font-size: 1.4rem;
  }
}

/* Medium devices (tablets, 768px and up)  */
@media (min-width: 768px) {
  .action-button {
    width: 10rem;
    font-size: 1.4rem;
  }
}

/* Large devices (desktops, 992px and up) */
@media (min-width: 992px) {
  .action-button {
    width: 12rem;
    font-size: 1.8rem;
  }
}
</style>
