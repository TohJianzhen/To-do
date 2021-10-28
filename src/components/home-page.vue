<template>
  <div>
    <div class="columns">
      <div class="column">
        <div class="content">
          <h1 class="is-size-1 has-text-left">Hello Jianzhen</h1>
        </div>
        <div>
          <input v-model="title" type="text" placeholder="Enter title">
            <button class="button" @click="addCategory()">+</button>
        </div>
      </div>
    </div>
    <div class="columns" id="category">
      <div class="column is-one-quarter" v-for="(category, index) in categories" :key="index">
        <div class="card">
          <div class="card-image">
            <figure class="image is-4by3">
              <img :src="category.img" alt="image">
            </figure>
          </div>
          <div class="card-content">
            <div class="media">
              <div class="media-content">
                <p class="title is-4">{{ category.title }}</p>
                <button>Delete</button>
              </div>
            </div>
          </div>
      </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function(){
    return{
      title: '',
      categories: [
        {
          title: 'First title',
          img: 'https://bulma.io/images/placeholders/1280x960.png'
        },
    ]}
  },
  methods: {
    addCategory(){
      if(this.title.length === 0){
        return;
      }
      else{
        this.categories.push({
          title: this.title,
          img: 'https://bulma.io/images/placeholders/1280x960.png'
        })
      }
    },
  }
}
</script>

<style scoped>
</style>
