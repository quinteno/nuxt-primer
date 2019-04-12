<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title" />
    </div>
    <p>
      {{ recipe.descriptionText }}
    </p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "Delicious burger",
              previewText: "This burger is amazing",
              descriptionText: "This is a really amazing dish!",
              thumbnail: "https://assets3.thrillist.com/v1/image/2797371/size/tl-horizontal_main_2x.jpg"
            },
            {
              id: "2",
              title: "Some noodles",
              previewText: "Here is a pic of some noodles",
              descriptionText: "This is a really amazing dish!",
              thumbnail: "https://ichef.bbci.co.uk/food/ic/food_16x9_832/recipes/one_pot_chorizo_and_15611_16x9.jpg"
            }
          ].find(el => el.id === context.params.id )
        })
      }, 1500)
    })
  }
}
</script>

<style scoped>
  .single-recipe {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
  }

  .recipe-image {
    width: 100%;
  }
</style>