<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h1>投票頁面</h1>

    <!-- 姓名輸入框 -->
    <label for="name">姓名:</label>
    <input type="text" id="name" v-model="name" />

    <!-- 選項 -->
    <div>
      <label>
        <input type="radio" v-model="voteOption" value="電腦" />
        電腦
      </label>
    </div>
    <div>
      <label>
        <input type="radio" v-model="voteOption" value="滑鼠" />
        滑鼠
      </label>
    </div>
        <!-- 投票按鈕 -->
    <button @click="vote">投票</button>

    <!-- 顯示投票結果 -->
    <div v-if="hasVoted">
      <p>{{ name }} 已投票給 {{ voteOption }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      voteOption: '',
      hasVoted: false
    }
  },
  methods: {
    vote() {
      console.log(`${this.name} 投票給 ${this.voteOption}`)
      this.hasVoted = true
    }
  }
}
</script>

<style>

</style>
