<template>
  <div class="nameBoard">
    <main v-bind:class="{normal:selectTab.normal}" class="nameBoard-container">
      <section v-bind:class="{active:selectTab.about}" v-on:click="switchTab()">
        <router-link to="/about" class="clickable">
          <div class="Tab-inner">
            <h2>00</h2>
            <h1>About Me</h1>
          </div>
          <div class="Board-inner">
            <h2>00</h2>
            <h1>About Me</h1>
          </div>
        </router-link>
        <router-view class="router"></router-view>
      </section>
      <section v-bind:class="{active:selectTab.project}" v-on:click="switchTab()">
        <router-link to="/project" class="clickable">
          <div class="Tab-inner">
            <h2>01</h2>
            <h1>Portfolio</h1>
          </div>
          <div class="Board-inner">
            <h2>01</h2>
            <h1>Portfolio</h1>
          </div>
        </router-link>
        <router-view class="router"></router-view>
      </section>
      <section v-bind:class="{active:selectTab.blog}" v-on:click="switchTab()">
        <router-link to="/blog" class="clickable">
          <div class="Tab-inner">
            <h2>02</h2>
            <h1>My Blog</h1>
          </div>
          <div class="Board-inner">
            <h2>02</h2>
            <h1>My Blog</h1>
          </div>
        </router-link>
        <router-view class="router"></router-view>
      </section>
      <section v-bind:class="{active:selectTab.ability}" v-on:click="switchTab()">
        <router-link to="/ability" class="clickable">
          <div class="Tab-inner">
            <h2>03</h2>
            <h1>Before Coding</h1>
          </div>
          <div class="Board-inner">
            <h2>03</h2>
            <h1>Before Coding</h1>
          </div>
        </router-link>
        <router-view class="router"></router-view>
      </section>
    </main>
  </div>
</template>
<script>
import store from "../store"
import tabCSS from "./tabCSS.scss"
export default {
	name: "resumeBoard",
	store,
	created() {
		this.switchTab()
	},
	methods: {
		switchTab() {
			for (let i in this.selectTab) {
				this.selectTab[i] = false
			}
			this.selectTab[this.$route.name] = true
		}
	},
	computed: {
		selectTab() {
			return this.$store.state.selectTab
		}
	}
}
</script>