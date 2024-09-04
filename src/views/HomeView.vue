<script>
export default {
  data() {
    return {
      searchArea: {
        quizName: "",
        startDate: "",
        endDate: "",
      },
      quizList: [],
      selectedQuizIds: []
    };
  },
  methods: {
    async search() {
      await this.saveData();
    },

    async saveData() {
      try {
        const response = await fetch('http://localhost:8080/quiz/search', { // 替換成你的後端API地址
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
          },
          body: JSON.stringify(this.searchArea), // 將this.data轉成JSON字串發送
        });
        if (response.ok) {
          console.log('數據保存成功！');
          // 處理成功響應（例如，顯示成功消息）
          console.log(response);
          const data = await response.json(); // 解析返回的 JSON 數據
          this.quizList = data.quizResList
          console.log('返回的數據:', data.quizResList);
          this.quizList.forEach(item => {
            item.state = this.determineSituation(item.startDate, item.endDate)
          })
          console.log(this.quizList)
          this.quizList = this.quizList.filter(p => p.published)
          console.log(this.quizList)

        } else {
          console.error('保存數據失敗。');
          // 處理失敗響應（例如，顯示錯誤消息）
        }
      } catch (error) {
        console.error('發生錯誤：', error);
        // 處理網路或其他錯誤
      }
      // this.back()
    },
    determineSituation(startDate, endDate) {
      const now = new Date();
      const start = new Date(startDate);
      const end = new Date(endDate);
      if (now < start) {
        return '尚未開始';
      } else if (now >= start && now <= end) {
        return '進行中';
      } else {
        return '已结束';
      }
    },
    editQuiz(item) {
      // 将问卷数据存储到 Session Storage
      sessionStorage.setItem('quizData', JSON.stringify({
        name: item.name,
        description: item.description,
        startDate: item.startDate,
        endDate: item.endDate,
        published: item.published,
        quesList: item.quesList
      }));
      // sessionStorage.getItem('quizData')
      console.log(sessionStorage.getItem('quizData'));

      this.$router.push('/FillinPage');
    },


    async saveAndPublish() {
      this.data.published = true; // 添加一個標記或屬性表示發布
      await this.saveData();
    },
    back() {
      // 使用 Vue Router 的 push 方法導航到 /next 頁面

      this.$router.push('/BackEnd');

    },
  }
}
</script>

<template>
  <div class="searchArea">
    <div class="enter">
      <p class="tree">問卷名稱:</p>
      <input v-model="searchArea.quizName" type="word" name="myfield" id="">
    </div>
    <div class="time">
      <p>統計時間:</p>
      <input v-model="searchArea.startDate" type="date" id="bookdate" name="">
      <p>到</p>
      <input v-model="searchArea.endDate" type="date" id="bookdate" name="">
      <button @click="search" class="press">搜尋</button>
    </div>
  </div>
  <div class="Group18">
    <table class="box">
      <tr>
        <!-- <td> </td> -->
        <td> 編號 </td>
        <td> 名稱 </td>
        <td> 狀態 </td>
        <td> 開始時間 </td>
        <td> 結束時間 </td>
        <td> 結果 </td>
      </tr>
      <tr v-for="item in this.quizList" :key="item.id">
        <!-- v-bind是會把裡面的東西設為變數 -->
        <!-- <td><input type="checkbox" v-model="selectedQuizIds" :id="item.id" :value="item.id"></td> -->

        <td>{{ item.id }}</td>
        <td>
          <a @click="editQuiz(item)">{{ item.name }}</a>
        </td>
        <!-- <td v-if="item.published">已發布</td>
                <td v-if="!item.published">未發布</td> -->
        <td>{{ item.state }}</td>
        <td>{{ item.startDate }}</td>
        <td>{{ item.endDate }}</td>
        <td>
          <RouterLink :to="{ name: 'StatisticPage', params: { id: item.id } }">{{ item.result }}</RouterLink>
        </td>
      </tr>
    </table>
  </div>
</template>


<style scoped lang="scss">
* {
  box-sizing: border-box;
  margin: 0px;
  padding: 0px;
}

body {
  overflow-x: hidden;
}

.searchArea {
  width: 550px;
  height: 150px;
  // border: 1px solid rgb(0, 0, 0);
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  border-radius: 40px;
  background-color: rgba(236, 255, 172, 0.918);
  margin-left: 470px;
  margin-top: 30px;

  .enter {
    width: 500px;
    height: 60px;
    // border: 1px solid rgb(0, 0, 0);
    padding-top: 5px;
    display: flex;
    padding-top: 10px;
    padding-left: 80px;

    input {
      width: 50%;
      height: 60%;
    }

    .word {
      font-size: 50px;
    }

    .tree {
      font-size: 20px;
    }
  }

  .time {
    width: 500px;
    height: 60px;
    // border: 1px solid rgb(0, 0, 0);
    font-size: 20px;
    padding-top: 5px;
    display: flex;
    padding-top: 15px;

    input {
      width: 30%;
      height: 50%;
    }

    button {
      width: 10%;
      height: 60%;
    }
  }
}

.Group18 {
  width: 600px;
  // height: 300px;
  // border: 1px solid rgb(0, 0, 0);
  margin-top: 30px;
  margin-left: 450px;


  .box {
    width: 600px;
    // height: 300px;
    // border: 1px solid rgb(0, 0, 0);
    background-color: rgba(255, 236, 222, 0.851);
    text-align: center;
    border-radius: 10px;
  }
}
</style>
