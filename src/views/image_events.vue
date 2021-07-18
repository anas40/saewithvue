<template>
  <main>
    <header>
      <h1 class="title">{{ event.name }}</h1>
      <div class="title-description">
        <p>
          {{event.description}}
        </p>
      </div>
    </header>
    <section>
      <div class="gallery">
        <div
          class="img-container"
          v-for="(value, index) in event.images"
          :key="index"
        >
          <img
            class="imagg"
            :src="
              require(`../assets/images/image_gallery/${event.name}/${value.name}`)
            "
            :alt="index"
          />
        </div>
      </div>
    </section>
  </main>
</template>
<script>
import store from "@/store.js";
export default {
  data() {
    return {
      event: null,
    };
  },
  props: {
    eventName: {
      type: String,
      required: true,
    },
  },
  created() {
    let eventName = this.eventName;
    console.log(eventName);
    this.event = store.events.find(function (event) {
      return event.name === eventName;
    });
    console.log(this.event.images);
  },
};
</script>

<style scoped>
.title {
  text-transform: capitalize;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  margin-top: 2em;
  text-align: center;
}
.title-description{
    padding: 1em;
}
.img-container {
  margin-top: 1em;
  border: 2px solid black;
  border-radius: 9px;
}
.img-container:last-child {
  margin-bottom: 1em;
}
.imagg {
  width: 100%;
  height:455px;
  object-fit: cover;
}
.gallery {
  flex-direction: column;
  display: flex;
  justify-content: space-evenly;
}
@media screen and (min-width: 991px) {
  .gallery {
    flex-wrap: wrap;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
  }
  .img-container {
    margin-top: 1em;
    width: 48%;
    border: 2px solid black;
    border-radius: 9px;
  }
}
</style>