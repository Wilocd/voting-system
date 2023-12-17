<template>
  <div class="home">
    <h1 class="page-title">線上投票系統</h1>

    <!-- 姓名輸入框 -->
    <div class="name-container">
      <label for="name" class="name-label">姓名:</label>
      <input type="text" id="name" v-model="name" class="name-input" />
    </div>

    <!-- 選項 -->
    <div class="options-container">
      <div class="option">
        <label class="checkbox-label">
          <input type="checkbox" v-model="selectedOptions" value="computer" />
          <img src="https://images.vexels.com/media/users/3/157318/isolated/lists/2782b0b66efa5815b12c9c637322aff3-desktop-computer-icon-computer.png" alt="電腦" />
        </label>
      </div>
      <div class="option">
        <label class="checkbox-label">
          <input type="checkbox" v-model="selectedOptions" value="mouse" />
          <img src="https://cdn-icons-png.flaticon.com/256/4854/4854338.png" alt="滑鼠" />
        </label>
      </div>
    </div>

    <!-- 投票按鈕 -->
    <button class="vote-button" @click="vote">投票</button>

    <!-- 顯示累積票數 -->
    <div class="vote-count">
      <label class="vote-label">電腦: {{ votes.computer }}</label>
      <label class="vote-label">滑鼠: {{ votes.mouse }}</label>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      selectedOptions: [],
      votes: {
        computer: 0,
        mouse: 0
      }
    }
  },
  methods: {
    vote() {
      // 累積票數
      this.selectedOptions.forEach(option => {
        this.votes[option]++
      })
    }
  }
}
</script>

<style>
.home {
  background-image: url('https://images.pexels.com/photos/912110/pexels-photo-912110.jpeg?cs=srgb&dl=pexels-elia-clerici-912110.jpg&fm=jpg');
  background-repeat: no-repeat;
  background-size: cover; /* 可以根據需要調整背景圖片的大小 */
  background-position: center; /* 使背景圖片居中 */
  background-attachment: fixed; /* 背景圖片固定在視窗中 */
  /* 其他樣式設定，如背景顏色、邊框等 */
}
.page-title {
  font-size: 90px; /* 調整字體大小為 24 像素，你可以根據需要調整數值 */
  color: black;
}
.name-container {
  display: flex;
  justify-content: center; /* 讓姓名標籤與輸入框水平置中 */
  align-items: center; /* 讓姓名標籤與輸入框垂直置中 */
  margin-top: 20px;
}
.name-label {
  font-size: 18px; /* 調整姓名標籤字體大小 */
  color: black;
  margin-right: 10px; /* 可調整姓名標籤與輸入框之間的間距 */
}
.name-input {
  font-size: 18px; /* 調整姓名輸入框字體大小 */
}
.options-container {
  display: flex;
  justify-content: center; /* 將選項水平置中 */
  align-items: center; /* 將選項垂直置中 */
  margin-top: 50px; /* 調整選項容器與上方元素的間距 */
  /* 調整其他 flex 屬性，如 justifyContent、alignItems，以達到你想要的排列效果 */
}

.option {
  /* 如果有需要，可以為每個選項添加額外樣式 */
  margin-right: 50px; /* 例如，添加右邊距，使選項之間有一定的間隔 */
  margin-bottom: 40px; /* 調整選項與下方元素的間距 */
}
.checkbox-label {
  display: flex;
  align-items: center;
}

.checkbox-label input[type="checkbox"] {
  transform: scale(2); /* 調整放大比例，你可以根據需要調整數值 */
}
.vote-button {
  font-size: 24px; /* 調整投票按鈕字體大小 */
  padding: 10px 30px; /* 調整投票按鈕內部間距 */
  margin-top: 20px;
}

.vote-count {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 20px;
  color: black;
}

.vote-label {
  font-size: 32px; /* 調整累積票數標籤字體大小 */
}
</style>
