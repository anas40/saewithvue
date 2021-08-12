<template>
  <main>
    <header>
      <h1 class="title">Image Gallery</h1>
    </header>
    <section>
      <div class="gallery">
        <div class="img-container" v-for="event in events" :key="event.id">
          <h1 class="img-container-title">{{event.name}}</h1>
          <router-link
                :to="{ name: 'image_events', params: { eventName: event.name } }"
              >
                <img
            class="imagg"
            v-lazy="require(`@/assets/images/image_gallery/${event.image}`)"
            :alt="event.id"
          />
              </router-link>
          <!-- <img
            class="imagg"
            v-lazy="require(`@/assets/images/image_gallery/${event.image}`)"
            :alt="event.id"
          /> -->
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
          image: "DSC_2842.jpg",
          // link: "cars/zfr-4.1",
          name:"Auto Expo 2018",
          id: 1,
        },
        {
          image: "_KEV7642.jpg",
          // link: "cars/zfr-4.1",
          name: "Formula Bharat 2020",
          id: 2,
        },
        {
          image: "IMG_20190717_164232.jpg",
          // link: "cars/zfr-4.1",
          name: "SUPRA SAE INDIA 2019",
          id: 3,
        },
        {
          image: "_DSC0508.jpg",
          // link: "cars/zfr-4.1",
          name: "Formula Student UK16",
          id: 4,
        },
        {
          image: "ab.jpg",
          // link: "cars/zfr-4.1",
          name: "Formula Student UK18",
          id: 5,
        }
      ],
    };
  },
};
</script>

<style>
.title {
  text-transform: capitalize;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-weight: 800;
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
   height: 455px;
  object-fit: cover;
}
.gallery {
  flex-direction: column;
  display: flex;
  justify-content: space-evenly;
}
.img-container-title{
    text-align: center;
    color: white;
    font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    background-color:black;
    margin-bottom: 0px;
}
@media screen and (min-width: 991px) {
  .gallery {
    flex-wrap: wrap;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
  }
  .img-container {
    width: 48%;
  }
  .img-container {
  margin-bottom: 1em;
}
}
</style>