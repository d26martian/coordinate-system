<template>
  <div class="home">
    <div class="container">
      <div class="row">
        <div class="col">
          <div class="home__title">
            <h1>Декартовая система координат</h1>
          </div>
        </div>
      </div>
      <div class="row m-bm">
        <div class="col">
          <Button text="задать входные данные" @onClick="handleClick" :active="active" />
        </div>
      </div>
      <div class="row">
        <div class="col">
          <Card v-if="show">
            <template v-slot:title>
              Введите координаты точек
            </template>
            <template v-slot:content>
              <div class="form">
                <form @submit.prevent="onSubmit">
                  <div class="form__control">
                    <Input label="X:" v-model="x" />
                  </div>
                  <div class="form__control">
                    <Input label="Y:" v-model="y" />
                  </div>
                  <div class="form__btn-group">
                    <Button text="Добавить" type="submit" />
                    <Button text="Обработать" @onClick="handleProcess" />
                  </div>
                </form>
              </div>
            </template>
          </Card>
        </div>
        <div class="col">
          <FieldCoord>
            <div class="dot" :style="styles"></div>
          </FieldCoord>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Card from '@/components/Card'
import Input from '@/components/UI/Input'
import Button from '@/components/UI/Button'
import FieldCoord from '@/components/FieldCoord'

export default {
  name: "Home",
  components: {
    Card,
    Input,
    Button,
    FieldCoord
  },
  data() {
    return {
      coord: {
        x: "",
        y: ""
      },
      x: "",
      y: "",
      show: false,
      active: false
    }
  },
  computed: {
    styles() {
      return {
        left: `${this.coord.x}px`,
        top: `${this.coord.y}px`
      }
    }
  },
  methods: {
    onSubmit() {
      this.coord.x = this.x
      this.coord.y = this.y
      this.x = ""
      this.y = ""
    },
    handleClick() {
      this.show = !this.show
      this.show ? this.active = true : this.active = false
    },
    handleProcess() {
      this.active = false
      this.show = false
    }
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

  &__btn-group {
    display: flex;
    justify-content: center;
    margin-left: -10px;
    margin-right: -10px;
  }
  &__btn-group .button {
    padding-left: 10px;
    padding-right: 10px;
    flex: 1;
  }
}

.dot {
  position: absolute;
  width: 5px;
  height: 5px;
  border-radius: 50%;
  background-color: green;
}
</style>