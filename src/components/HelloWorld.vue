<template>
  <div class="hello">
    <b-container>
      <b-form class="text-justify">
        <b-col sm="7" class="input mx-auto">
          <myTextarea
              :maximumLength="maximumLength"
              @setTextLength="setTextLength"
          />
          <myFormLabel
              :textLength="textLength"
              :maximumLength="maximumLength"
              :labelClass="labelClass"
          />
        </b-col>
        <myButton
          :isDisabled="maximumAchieved"
        />
      </b-form>
    </b-container>
  </div>
</template>

<script>
import MyFormLabel from '@/components/home/MyFormLabel.vue';
import MyButton from '@/components/home/MyButton.vue';
import MyTextarea from '@/components/home/MyTextarea.vue'
export default {
  components: {
    MyFormLabel,
    MyButton,
    MyTextarea
  },
  name: 'HelloWorld',
  data: () => ({
    maximumLength: 40,
    warningLength: 30,
    textLength: 0
  }),
  computed: {
    labelClass: function () {
      let labelClass = 'success';
      if (this.textLength > this.maximumLength) {
        labelClass = 'danger'
      } else if (this.textLength >= this.warningLength) {
        labelClass = 'warning'
      }
      return labelClass
    },
    maximumAchieved: function () {
      return (this.textLength > this.maximumLength)
    }
  },
  methods: {
    setTextLength (textLength) {
      this.textLength = textLength
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.input {
  margin-top: 10px;
  margin-bottom: 10px;
}
</style>
