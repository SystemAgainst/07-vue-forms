<script setup>
// import HelloWorld from "./components/HelloWorld.vue";
// import TheWelcome from "./components/TheWelcome.vue";
</script>

<template>
  <div class="container">
    <form class="card" @click.prevent="submitHandler">
      <h1>Анкета на Vue разработчика!</h1>
      <div class="form-control">
        <label for="name">Как тебя зовут?</label>
        <input
          type="text"
          id="name"
          placeholder="Введи имя"
          v-model.trim="name"
        />
      </div>

      <div class="form-control">
        <label for="age">Выбери возраст</label>
        <input type="number" id="age" max="70" v-model.number="age" />
      </div>

      <div class="form-control">
        <label for="city">Твой город</label>
        <select id="city" v-model="city">
          <option value="spb">Санкт-Петербург</option>
          <option value="msk">Москва</option>
          <option value="kzn">Казань</option>
          <option value="nsk">Новосибирск</option>
        </select>
      </div>

      <div class="form-checkbox">
        <span class="label">Готов к переезду в Токио?</span>
        <div class="checkbox">
          <label
            ><input type="radio" v-model="relocate" name="trip" value="yes" />
            Да</label
          >
        </div>

        <div class="checkbox">
          <label
            ><input type="radio" v-model="relocate" name="trip" value="no" />
            Нет</label
          >
        </div>
      </div>

      <div class="form-checkbox">
        <span class="label">Что знаешь во Vue?</span>
        <div class="checkbox">
          <label
            ><input type="checkbox" v-model="skills" value="vuex" /> Vuex</label
          >
        </div>
        <div class="checkbox">
          <label
            ><input type="checkbox" v-model="skills" value="cli" /> Vue
            CLI</label
          >
        </div>
        <div class="checkbox">
          <label
            ><input type="checkbox" v-model="skills" value="router" /> Vue
            Router</label
          >
        </div>
      </div>

      <div class="form-checkbox">
        <span class="label">Правила компании</span>
        <div class="checkbox">
          <label
            ><input type="checkbox" v-model="agree" /> С правилами
            согласен</label
          >
        </div>
      </div>

      <button type="submit" class="btn primary">Отправить</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      age: 23,
      city: "spb",
      relocate: "",
      skills: [],
      agree: null,
    };
  },
  methods: {
    submitHandler() {
      console.group("Form Data");
      console.log("Name: ", this.name);
      console.log("Age: ", this.age);
      console.log("City: ", this.city);
      console.log("To Tokyo: ", this.relocate);
      console.log("Skills: ", this.skills);
      console.log("Agree: ", this.agree);
      console.groupEnd();
    },
  },
};
</script>

<style scoped></style>
