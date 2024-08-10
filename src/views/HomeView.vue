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
      },
      {
        number: 447,
        name: "購買傾項市調",
        situation: "尚未開始",
        dateStart: "2023/11/12",
        dateEnd: "2024/05/02",
        result: "前往"
      },
      {
        number: 448,
        name: "青春洋溢高中生",
        situation: "進行中",
        dateStart: "2023/12/05",
        dateEnd: "2024/03/02",
        result: "前往"
      },
      {
        number: 449,
        name: "尾牙餐廳預選",
        situation: "已結束",
        dateStart: "2023/01/05",
        dateEnd: "2024/06/02",
        result: "前往"
      },
      {
        number: 450,
        name: "購買傾項市調",
        situation: "尚未開始",
        dateStart: "2023/11/12",
        dateEnd: "2024/05/02",
        result: "前往"
      },
      {
        number: 451,
        name: "青春洋溢高中生",
        situation: "進行中",
        dateStart: "2023/12/05",
        dateEnd: "2024/03/02",
        result: "前往"
      },
      {
        number: 452,
        name: "尾牙餐廳預選",
        situation: "已結束",
        dateStart: "2023/01/05",
        dateEnd: "2024/06/02",
        result: "前往"
      },
      ],
      currentPage: 1,  // 當前頁數
      itemsPerPage: 3, // 每頁顯示的項目數量
      searchQuery: '', // 搜索查詢
      startDate: '',   // 開始日期
      endDate: '',     // 結束日期
    };
  },
  computed: {
    // 計算分頁後的項目
    paginatedItems() {
      let start = (this.currentPage - 1) * this.itemsPerPage;
      let end = start + this.itemsPerPage;
      return this.pageArray.slice(start, end);
    },
    // 計算總頁數
    totalPages() {
      return Math.ceil(this.pageArray.length / this.itemsPerPage);//Math.ceil無條件進位法
    }
  },
  methods: {
    // 切換到上一頁
    prevPage() {
      if (this.currentPage > 1) {
        this.currentPage--;
      }
    },
    // 切換到下一頁
    nextPage() {
      if (this.currentPage < this.totalPages) {
        this.currentPage++;
      }
    },
    // 切換到指定頁數
    goToPage(page) {
      if (page >= 1 && page <= this.totalPages) {
        this.currentPage = page;
      }
    }
  }
}
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
      <tr v-for="item in this.paginatedItems">
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
    <a @click.prevent="prevPage" :disabled="currentPage === 1">&lt;</a>
    <a href="" v-for="page in totalPages" :key="page" @click.prevent="goToPage(page)">

      {{ page }}
    </a>
    <a @click.prevent="nextPage" :disabled="currentPage === totalPages">&gt;</a>

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
  margin-left: 400px;
  margin-top: 50px;

  .enter {
    width: 500px;
    height: 60px;
    border: 1px solid rgb(0, 0, 0);
    display: flex;
    padding-top: 15px;
    padding-left: 20px;


    input {
      width: 70%;
      height: 60%;
      margin-top: 1px;
      margin-left: 2px;
    }

    .word {
      font-size: 40px;
    }

    .tree {
      font-size: 20px;
    }
  }

  .time {
    width: 500px;
    height: 60px;
    border: 1px solid rgb(0, 0, 0);
    padding-top: 5px;
    display: flex;
    padding-top: 15px;
    font-size: 20px;

    input {
      width: 30%;
      height: 50%;
      font-size: 15px;
    }

    button {
      width: 10%;
      height: 60%;
      margin-left: 20px;
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
  justify-content: space-evenly;
  align-items: center;
}
</style>
