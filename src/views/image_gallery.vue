<template>
  <main>
    <header>
      <h1 class="title">our image gallery</h1>
    </header>
    <section>
      <div class="gallery">
        <div class="img-container" v-for="event in events" :key="event.id">
          <img
            class="imagg"
            v-lazy="require(`@/assets/images/image_gallery/${event.image}`)"
            :alt="event.id"
          />
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  data() {
    return {
      events: [
        {
          image: "_KEV7642.jpg",
          // link: "cars/zfr-4.1",
          // name: "ZFR 4.1",
          id: 1,
        },
        {
          image: "DSC_0006.NEF.jpg",
          // link: "cars/zfr-4.1",
          // name: "ZFR 4.1",
          id: 2,
        },
        {
          image: "DSC_0282.NEF.jpg",
          // link: "cars/zfr-4.1",
          // name: "ZFR 4.1",
          id: 3,
        },
        {
          image: "DSC_0322.NEF.jpg",
          // link: "cars/zfr-4.1",
          // name: "ZFR 4.1",
          id: 4,
        },
        {
          image: "DSC_0341.NEF.jpg",
          // link: "cars/zfr-4.1",
          // name: "ZFR 4.1",
          id: 5,
        },
        {
          image: "DSC_0688.NEF.jpg",
          // link: "cars/zfr-4.1",
          // name: "ZFR 4.1",
          id: 6,
        },
        {
          image: "DSC_0738.NEF.jpg",
          // link: "cars/zfr-4.1",
          // name: "ZFR 4.1",
          id: 7,
        },
      ],
    };
  },
};
</script>

<style>
.title {
  text-transform: capitalize;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  margin-top: 2em;
  text-align: center;
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