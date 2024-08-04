<script>
export default {
  data() {

    return {
      pageArray: [{
        number: 444,
        name: "購買傾項市調",
        situation: "尚未開始",
        dateStart: "2023/11/12",
        dateEnd: "2024/05/02",
        result: "前往"
      },
      {
        number: 445,
        name: "青春洋溢高中生",
        situation: "進行中",
        dateStart: "2023/12/05",
        dateEnd: "2024/03/02",
        result: "前往"
      },
      {
        number: 446,
        name: "尾牙餐廳預選",
        situation: "已結束",
        dateStart: "2023/01/05",
        dateEnd: "2024/06/02",
        result: "前往"
      }
      ]
    };
  },
  methods: {

  },
};
</script>

<template>
  <div class="searchArea">
    <div class="enter">
      <p class="tree">問卷名稱:</p>
      <input type="word" name="myfield" id="">
    </div>
    <div class="time">
      <p>統計時間:</p>
      <input type="date" id="bookdate" name="">
      <p>到</p>
      <input type="date" id="bookdate" name="">
      <button class="press">搜尋</button>
    </div>
  </div>
  <div class="Group18">
    <table class="box">
      <tr>
        <td> 編號 </td>
        <td> 名稱 </td>
        <td> 狀態 </td>
        <td> 開始時間 </td>
        <td> 結束時間 </td>
        <td> 結果 </td>
      </tr>
      <tr v-for="item in this.pageArray">
        <td> {{ item.number }} </td>
        <td> {{ }} <RouterLink to="/InsidePage">{{ item.name }}</RouterLink>
        </td>
        <td>{{ item.situation }}</td>
        <td>{{ item.dateStart }}</td>
        <td>{{ item.dateEnd }}</td>
        <td>{{ }} <RouterLink to="/StatisticPage">{{ item.result }}</RouterLink>
        </td>
      </tr>
    </table>
  </div>
  <div class="page">
    <p></p>
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
  width: 600px;
  height: 150px;
  border: 1px solid rgb(0, 0, 0);
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  margin-left: 500px;
  margin-top: 50px;

  .enter {
    width: 500px;
    height: 60px;
    border: 1px solid rgb(0, 0, 0);
    display: flex;
    padding-top: 15px;


    input {
      width: 70%;
      height: 80%;
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
    border: 1px solid rgb(0, 0, 0);
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
  height: 300px;
  border: 1px solid rgb(0, 0, 0);
  margin-left: 400px;
  margin-top: 50px;

  .box {
    width: 600px;
    height: 300px;
    border: 1px solid rgb(0, 0, 0);
    text-align: center;
    background-color: rgb(245, 255, 136);
  }
}

.page {
  width: 714px;
  height: 28px;
  border: 1px solid rgb(0, 0, 0);
  display: flex;
  margin-left: 350px;
  margin-top: 40px;
  background-color: rgb(227, 255, 181);
}
</style>
