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
        <div class="circle3">
            <p>問卷回饋</p>
        </div>
        <div class="circle4">
            <p>統計</p>
        </div>
    </div>
    <div class="Group1">
        <div class="oval0">
            <div class="oval1">
                <p>問卷名稱:</p>
                <input type="text">
            </div>
        </div>
        <!-- <div class="oval1">
            <p>問卷名稱:</p>
            <input type="text">
        </div> -->
        <div class="oval2">
            <p>問卷說明:</p>
            <textarea name="" id=""></textarea>
        </div>
        <div class="oval3">
            <p>開始時間:</p>
            <input type="date" id="bookdate" name="">
        </div>
        <div class="oval4">
            <p>結束時間:</p>
            <input type="date" id="bookdate" name="">
        </div>
        <div class="Group2">
            <div class="bean1">
                <button class="Cancel">取消</button>
            </div>
            <div class="bean2">
                <button class="next">下一步</button>
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
}

.Group1 {
    width: 1000px;
    height: 500px;
    border: 1px solid rgb(0, 0, 0);
    margin-left: 200px;
    display: flex;
    // justify-content: space-between;
    flex-direction: column;
    position: relative;

    .oval0 {
        width: 900px;
        height: 100px;
        // border: 1px solid rgb(0, 0, 0);
        display: flex;
        flex-direction: column;

        .oval1 {
            width: 900px;
            height: 100px;
            // border: 1px solid rgb(0, 0, 0);
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 30px;
            padding-right: 100px;

            input {
                width: 500px;
                height: 60px;
            }
        }
    }

    .oval2 {
        width: 900px;
        height: 150px;
        // border: 1px solid rgb(0, 0, 0);
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 30px;

        textarea {
            width: 599px;
            height: 137px;
            resize: none;
        }
    }

    .oval3 {
        width: 900px;
        height: 100px;
        // border: 1px solid rgb(0, 0, 0);
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 30px;
        padding-right: 350px;

        input {
            font-size: 30px;
        }
    }

    .oval4 {
        width: 900px;
        height: 100px;
        // border: 1px solid rgb(0, 0, 0);
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 30px;
        padding-right: 350px;

        input {
            font-size: 30px;
        }

    }

    .Group2 {
        width: 900px;
        height: 50px;
        // border: 1px solid rgb(0, 0, 0);
        display: flex;
        justify-content: right;

        .bean1 {
            width: 200px;
            height: 50px;
            // border: 1px solid rgb(0, 0, 0);
            display: flex;
            justify-content: center;
            align-items: center;

            .Cancel {
                width: 100px;
                height: 30px;
            }
        }

        .bean2 {
            width: 200px;
            height: 50px;
            // border: 1px solid rgb(0, 0, 0);
            display: flex;
            justify-content: center;
            align-items: center;

            .next {
                width: 100px;
                height: 30px;
            }
        }
    }
}
</style>