<template>
  <div class="home">
    <div class="container">
      <div class="row">
        <div class="col">
          <div class="home__title">
            <h1>декартовой системе координат</h1>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col">
          <Card>
            <template v-slot:title>
              Введите координаты точек
            </template>
            <template v-slot:content>
              <div class="form">
                <form @submit.prevent="onSubmit">
                  <div class="form__control">
                    <Input label="X:" @input="onInputX" />
                  </div>
                  <div class="form__control">
                    <Input label="Y:" @input="onInputY" />
                  </div>
                  <Button text="Задать" type="submit" />
                </form>
              </div>
            </template>
          </Card>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Card from '@/components/Card'
import Input from '@/components/UI/Input'
import Button from '@/components/UI/Button'

export default {
  name: "Home",
  components: {
    Card,
    Input,
    Button
  },
  data() {
    return {
      coord: {
        x: "",
        y: ""
      }
    }
  },
  methods: {
    onInputX(event) {
      this.coord.x = event.target.value
    },
    onInputY(event) {
      this.coord.y = event.target.value
    },
    onSubmit() {
      console.log('send', this.coord)
    },
  }
}
</script>
<style lang="scss">
.home {
  padding: 30px 50px 0;

  &__title {

    margin-bottom: 50px;
  }
}
.form {
  &__control {
    margin-bottom: 15px;
  }
}

</style>