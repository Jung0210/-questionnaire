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
</template>
< style scoped lang="scss">
  * {
  box-sizing: border-box;
  margin: 0px;
  padding: 0px;
  }

  // body {
  // overflow-x: hidden;
  // }

  .searchArea {
  width: 1520px;
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
  }
  }

  </style>