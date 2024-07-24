<script>

</script>

<template>
    <div class="first">
        <p>青春洋溢高中生人氣投票戰</p>
    </div>
    <div class="shape">
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae tempora eos dolores labore cupiditate
            fuga iure, inventore harum voluptas nostrum, rem animi eaque minima atque sit velit expedita. Vero, non.</p>
    </div>
    <div class="container">
        <div class="chocolate">
            <div class="box">
                <p>姓名:</p>
            </div>
            <div class="box1">
                <p>手機:</p>
            </div>
            <div class="box2">
                <p>E-mail:</p>
            </div>
            <div class="box3">
                <p>年齡:</p>
            </div>
        </div>
        <div class="enter">
            <div class="line">
                <input type="one">
            </div>
            <div class="line1">
                <input type="one">
            </div>
            <div class="line2">
                <input type="one">
            </div>
            <div class="line3">
                <input type="one">
            </div>
        </div>
    </div>
    <div class="Group15">
        <div class="team">
            <p>請選取最喜歡的人(必填)</p>
        </div>
        <div class="team1">
            <input type="word" name="myfield" id="">
        </div>
    </div>
    <div class="Group13">
        <div class="area">
            <p>請說明理由</p>
        </div>
        <div class="area1">
            <textarea name="" id=""></textarea>
        </div>
        <!-- <div class="area1">
            <textarea class="charger" id="">51131</textarea>
        </div> -->
    </div>
    <div class="Group12">
        <div class="bee">
            <p>3.請選取在活動開始前有聽過的人(必填)</p>
        </div>
        <div class="bee1">
            <input type="" id="" name=""></input>
        </div>
        <div class="bee2">
            <input type="" id="" name=""></input>
        </div>
        <div class="bee3">
            <input type="" id="" name=""></input>
        </div>
    </div>
    <div class="Group10">
        <div class="egg1">
            <button class="Cancel">修改</button>
        </div>
        <div class="egg2">
            <button class="send">送出</button>
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

.first {
    width: 1500px;
    height: 60px;
    border: 1px solid rgb(0, 0, 0);
    background-color: rgb(255, 255, 255);

    p {
        font-size: 20px;
        text-align: center;
        padding-top: 15px;
    }
}

.shape {
    width: 1000px;
    height: 80px;
    border: 1px solid rgb(0, 0, 0);
    background-color: rgb(255, 255, 255);
    margin-top: 20px;
    margin-left: 260px;
}

.container {
    width: 900px;
    height: 200px;
    border: 1px solid rgb(0, 0, 0);
    margin-top: 20px;
    display: flex;
    margin-left: 300px;

    .chocolate {
        width: 350px;
        height: 198px;
        border: 1px solid rgb(0, 0, 0);
        display: flex;
        flex-direction: column;
        justify-content: space-around;

        .box {
            width: 349px;
            height: 40px;
            border: 1px solid rgb(0, 0, 0);
            font-size: 20px;
            text-align: center;
        }

        .box1 {
            width: 349px;
            height: 40px;
            border: 1px solid rgb(0, 0, 0);
            font-size: 20px;
            text-align: center;
        }

        .box2 {
            width: 349px;
            height: 40px;
            border: 1px solid rgb(0, 0, 0);
            font-size: 20px;
            text-align: center;
        }

        .box3 {
            width: 349px;
            height: 40px;
            border: 1px solid rgb(0, 0, 0);
            font-size: 20px;
            text-align: center;
        }
    }

    .enter {
        width: 1000px;
        height: 200px;
        border: 1px solid rgb(0, 0, 0);
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;

        .line {
            width: 500px;
            height: 40px;
            border: 1px solid rgb(0, 0, 0);
        }

        .line1 {
            width: 500px;
            height: 40px;
            border: 1px solid rgb(0, 0, 0);
        }

        .line2 {
            width: 500px;
            height: 40px;
            border: 1px solid rgb(0, 0, 0);
        }

        .line3 {
            width: 500px;
            height: 40px;
            border: 1px solid rgb(0, 0, 0);
        }

        input {
            width: 500px;
            height: 40px;
        }
    }
}

.Group15 {
    width: 400px;
    height: 100px;
    border: 1px solid rgb(0, 0, 0);
    display: flex;
    flex-direction: column;
    margin-top: 15px;
    margin-left: 300px;

    .team {
        width: 400px;
        height: 40px;
        border: 1px solid rgb(0, 0, 0);
    }

    .team1 {
        width: 400px;
        height: 100px;
        border: 1px solid rgb(0, 0, 0);
        padding-top: 10px;
        justify-content: center;
        display: flex;
        justify-content: space-between;

        input {
            width: 3300px;
            height: 35px;
            border: 1px solid rgb(0, 0, 0);
        }
    }
}

.Group13 {
    width: 400px;
    height: 120px;
    border: 1px solid rgb(0, 0, 0);
    display: flex;
    flex-direction: column;
    margin-top: 20px;
    margin-left: 300px;

    .area {
        width: 400px;
        height: 40px;
        text-align: left;

        p {
            font-size: 18px;
            text-align: left;
        }
    }

    .area1 {
        width: 398px;
        height: 190px;
        padding-top: 10px;
        border: 1px solid rgb(0, 0, 0);
        position: relative;
        display: flex;
        justify-content: space-between;

        textarea {
            width: 350px;
            height: 70px;
            border: 1px solid rgb(0, 0, 0);
            resize: none;
            position: absolute;
            left: 7px;
            top: 9px;

        }
    }
}

.Group12 {
    width: 500px;
    height: 250px;
    border: 1px solid rgb(0, 0, 0);
    margin-top: 30px;
    margin-left: 300px;
    display: flex;
    justify-content: space-around;
    flex-direction: column;
    text-align: left;

    .bee {
        width: 450px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
    }

    .bee1 {
        width: 450px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        display: flex;
        justify-content: space-between;
        align-items: center;


        input {
            width: 350px;
            height: 35px;
            border: 1px solid rgb(0, 0, 0);
        }

    }

    .bee2 {
        width: 450px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        display: flex;
        justify-content: space-between;
        align-items: center;

        input {
            width: 350px;
            height: 35px;
            border: 1px solid rgb(0, 0, 0);
        }
    }

    .bee3 {
        width: 450px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        display: flex;
        justify-content: space-between;
        align-items: center;

        input {
            width: 350px;
            height: 35px;
            border: 1px solid rgb(0, 0, 0);
        }
    }

}

.Group10 {
    width: 400px;
    height: 50px;
    border: 1px solid rgb(0, 0, 0);
    margin-top: 25px;
    margin-left: 1000px;
    display: flex;

    .egg1 {
        width: 200px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        display: flex;
        justify-content: center;
        align-items: center;

        .Cancel {
            width: 100px;
            height: 30px;
        }
    }

    .egg2 {
        width: 200px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        display: flex;
        justify-content: center;
        align-items: center;

        .send {
            width: 100px;
            height: 30px;
        }
    }
}
</style>
