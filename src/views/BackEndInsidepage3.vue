<script>

</script>

<template>
    <div class="Group0">
        <div class="circle1">
            <p>問卷</p>
        </div>
        <div class="circle2">
            <p>題目</p>
        </div>
        <div class="circle3" :class="{ 'bgColor': this.$route.path == '/BackEndInsidePage3' }">
            <p>問卷回饋</p>
        </div>
        <div class="circle4">
            <p>統計</p>
        </div>
    </div>
    <div class="Group1">
        <div class="Group2">
            <div class="box0">
                <table class="box1">
                    <tr>
                        <td>編號</td>
                        <td>內容</td>
                        <td>填寫時間</td>
                        <td>觀看回覆</td>
                    </tr>
                    <tr>
                        <td>#1</td>
                        <td> 小華 </td>
                        <td> 1111</td>
                        <td> 前往 </td>
                    </tr>
                    <tr>
                        <td> #2</td>
                        <td> 大明 </td>
                        <td>1111 </td>
                        <td> 前往</td>
                    </tr>
                    <tr>
                        <td> #3</td>
                        <td> 大頭 </td>
                        <td> 111</td>
                        <td> 前往 </td>
                    </tr>
                </table>
                <div class="square"></div>
            </div>
        </div>
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

.Group0 {
    width: 1000px;
    height: 50px;
    // border: 1px solid rgb(0, 0, 0);
    display: flex;
    margin-left: 200px;
    margin-top: 40px;

    .circle1 {
        width: 150px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        border-top-left-radius: 10px;
        border-top-right-radius: 10px;
        background-color: #e2e2e2;
        text-align: center;
        font-size: 30px;

        &:hover {
            background-color: rgb(255, 255, 255);
        }

    }

    .circle2 {
        width: 150px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        border-top-left-radius: 10px;
        border-top-right-radius: 10px;
        background-color: #e2e2e2;
        text-align: center;
        font-size: 30px;

        &:hover {
            background-color: rgb(255, 255, 255);
        }
    }

    .circle3 {
        width: 150px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        border-top-left-radius: 10px;
        border-top-right-radius: 10px;
        background-color: #e2e2e2;
        text-align: center;
        font-size: 30px;

        &:hover {
            background-color: rgb(255, 255, 255);
        }
    }

    .circle4 {
        width: 150px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        border-top-left-radius: 10px;
        border-top-right-radius: 10px;
        background-color: #e2e2e2;
        text-align: center;
        font-size: 30px;

        &:hover {
            background-color: rgb(255, 255, 255);
        }

    }

    .bgColor {
        background-color: white;
    }
}

.Group1 {
    width: 1000px;
    height: 500px;
    border: 1px solid rgb(0, 0, 0);
    margin-left: 200px;
    display: flex;
    // justify-content: space-between;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    .Group2 {
        width: 500px;
        height: 200px;
        border: 1px solid rgb(0, 0, 0);
        display: flex;
        flex-direction: column;

        .box1 {
            width: 500px;
            height: 200px;
            border: 1px solid rgb(0, 0, 0);
        }
    }

    .square {
        width: 600px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        margin-top: 40px;
        margin-left: -66px;
    }
}
</style>