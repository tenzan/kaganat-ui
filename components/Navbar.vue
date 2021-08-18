<template>
  <b-navbar>
    <template #brand>
      <b-navbar-item tag="router-link" :to="{ path: '/' }">
        <!-- <img
          src="https://raw.githubusercontent.com/buefy/buefy/dev/static/img/buefy-logo.png"
          alt="Lightweight UI components for Vue.js based on Bulma"
        /> -->
        Kaganat.com
      </b-navbar-item>
    </template>
    <template #start>
      <b-navbar-item href="/"> Главная </b-navbar-item>
      <b-navbar-item href="#"> Категории </b-navbar-item>
      <b-navbar-dropdown label="Инфо">
        <b-navbar-item href="#"> О нас </b-navbar-item>
        <b-navbar-item href="#"> Контакты </b-navbar-item>
      </b-navbar-dropdown>
    </template>

    <template #end>
      <b-navbar-item tag="div">
        <div class="buttons">
          <a class="button is-primary">
            <strong>Sign up</strong>
          </a>
          <a class="button is-light"> Log in </a>
        </div>
      </b-navbar-item>
    </template>
  </b-navbar>
</template>
