<template>
  <video autoplay muted loop class="background-video">
    <source
      src="https://videos.pexels.com/video-files/4625179/4625179-uhd_1440_2560_30fps.mp4"
      type="video/mp4"
    />
  </video>
  <div class="button-container">
    <h1>Pick your choosing ;)</h1>
    <div class="buttons-grid">
      <div
        class="button-pair"
        v-for="(pair, index) in buttonPairs"
        :key="index"
      >
        <button
          :class="{ highlighted: selectedOptions[index] === pair.option1 }"
          @click="handleClick(pair.option1, index)"
        >
          {{ pair.option1Text }}
        </button>
        <button
          :class="{ highlighted: selectedOptions[index] === pair.option2 }"
          @click="handleClick(pair.option2, index)"
        >
          {{ pair.option2Text }}
        </button>
      </div>
    </div>

    <!-- Show the heart-shaped message if all selections are made -->
    <div v-if="allOptionsSelected" class="message-popup">
      <div class="heart-message">
        <p>Congratulations, you planned your perfect valentine!</p>
        <p>What: {{ selectedOptions[0] }}</p>
        <p>Gifts: {{ selectedOptions[1] }}</p>
        <p>Dessert for after: {{ selectedOptions[2] }}</p>
        <p>When: {{ selectedOptions[3] }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedOptions: [],
      buttonPairs: [
        {
          option1: "Dinner Date Night",
          option1Text: "Dinner Date Night",
          option2: "Movie Date Night",
          option2Text: "Movie Date Night",
        },
        {
          option1: "Chocolates & Candy",
          option1Text: "Chocolates & Candy",
          option2: "Clothes",
          option2Text: "Clothes",
        },
        {
          option1: "Dessert: Ice cream",
          option1Text: "Ice cream",
          option2: "Dessert: Cake",
          option2Text: "Cake",
        },
        {
          option1: "Saturday Feb. 15",
          option1Text: "Saturday Feb. 15",
          option2: "Friday Feb 14",
          option2Text: "Friday Feb 14",
        },
      ],
    };
  },
  computed: {
    allOptionsSelected() {
      return this.selectedOptions.length === this.buttonPairs.length;
    },
  },
  methods: {
    handleClick(option, index) {
      if (!this.selectedOptions[index]) {
        this.selectedOptions[index] = option;
      }
    },
  },
};
</script>

<style scoped>
.button-container {
  text-align: center;
  margin-top: 50px;
  font-family: Arial, sans-serif;
}

h1 {
  margin-bottom: 20px;
}

.buttons-grid {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
  margin-top: 20px;
}

.button-pair {
  display: flex;
  gap: 10px;
}

button {
  font-size: 16px;
  padding: 10px 20px;
  background-color: #f4b5b7;
  color: black;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #ff7986;
}

/* Highlighted button styles */
button.highlighted {
  background-color: #ff7986;
  color: white;
}

.results {
  margin-top: 30px;
}

.results p {
  font-size: 18px;
  color: #333;
  margin: 5px 0;
}

/* Popup and heart shape message */
.message-popup {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.heart-message {
  background: white;
  padding: 20px;
  border-radius: 15px;
  text-align: center;
  max-width: 400px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
}

.heart-message p {
  font-size: 18px;
  color: #ff4c8b;
  font-weight: bold;
}
</style>
