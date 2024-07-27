<script>

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
      <tr>
        <td> #444 </td>
        <td> 購買頃項市調 </td>
        <td> 尚未開始 </td>
        <td> 2023/11/12 </td>
        <td> 2024/5/2 </td>
        <td> 前往 </td>
      </tr>
      <tr>
        <td> #445 </td>
        <td>
          <RouterLink to="/ConfirmationPage">青春洋溢高中生</RouterLink>
        </td>
        <td> 進行中 </td>
        <td> 2023/12/5 </td>
        <td> 2024/3/2 </td>
        <td>
          <RouterLink to="/StatisticPage">前往</RouterLink>
        </td>
      </tr>
      <tr>
        <td> #446 </td>
        <td> 尾牙餐廳預選 </td>
        <td> 已結束 </td>
        <td> 2023/1/5 </td>
        <td> 2023/6/2 </td>
        <td> 前往 </td>
      </tr>
      <tr>
        <td> #447 </td>
        <td> 中秋禮盒預選 </td>
        <td> 已結束 </td>
        <td> 2023/3/5 </td>
        <td> 2023/7/2 </td>
        <td> 前往 </td>
      </tr>
      <tr>
        <td> #448 </td>
        <td> 購買傾項市調 </td>
        <td> 已結束 </td>
        <td> 2023/5/5 </td>
        <td> 2023/8/2 </td>
        <td> 前往 </td>
      </tr>
      <tr>
        <td> #449 </td>
        <td> 最佳員工 </td>
        <td> 已結束 </td>
        <td> 2024/3/5 </td>
        <td> 2024/7/2 </td>
        <td> 前往 </td>
      </tr>
      <tr>
        <td> #450 </td>
        <td> 大會參加統計 </td>
        <td> 已結束 </td>
        <td> 2024/2/5 </td>
        <td> 2024/6/2 </td>
        <td> 前往 </td>
      </tr>
      <tr>
        <td> #451 </td>
        <td> 第六期好員工票選 </td>
        <td> 已結束 </td>
        <td> 2024/2/5 </td>
        <td> 2024/6/2 </td>
        <td> 前往 </td>
      </tr>
      <tr>
        <td> #452 </td>
        <td> 會議參加統計 </td>
        <td> 已結束 </td>
        <td> 2024/2/5 </td>
        <td> 2024/6/2 </td>
        <td> 前往 </td>
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
  width: 1500px;
  height: 150px;
  border: 1px solid rgb(0, 0, 0);
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;

  .enter {
    width: 1300px;
    height: 60px;
    border: 1px solid rgb(0, 0, 0);
    padding-top: 5px;
    display: flex;
    padding-top: 10px;

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
    width: 1300px;
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
  width: 1500px;
  height: 500px;
  border: 1px solid rgb(0, 0, 0);
  margin-top: 10px;

  .box {
    width: 1500px;
    height: 500px;
    border: 1px solid rgb(0, 0, 0);
    text-align: center;
  }
}

.page {
  width: 714px;
  height: 28px;
  border: 1px solid rgb(0, 0, 0);
  display: flex;
  margin-left: 380px;
  margin-top: 15px;
  padding-left: 200px;
}
</style>
