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

  </div>
  <div class="page">
    <p>
      << | < | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |> | >>
    </p>
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
}

.page {
  width: 714px;
  height: 28px;
  border: 1px solid rgb(0, 0, 0);
  display: flex;
  margin-left: 300px;
  margin-top: 10px;
  padding-left: 200px;
}
</style>
