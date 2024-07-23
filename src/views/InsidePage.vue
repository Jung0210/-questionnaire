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
            <input type="checkbox" id="" name=""> 14545 </input>
        </div>
        <div class="team2">
            <input type="checkbox" id="" name=""> 326656 </input>
        </div>
        <div class="team3">
            <input type="checkbox" id="" name=""> 454545 </input>
        </div>
        <div class="team4">
            <input type="checkbox" id="" name=""> 889897 </input>
        </div>
    </div>
    <div class="Group13">
        <div class="area">
            <p>請說明理由</p>
        </div>
        <div class="area1">
            <textarea class="charger" id="">51131</textarea>
        </div>
    </div>
    <div class="Group12">
        <div class="bee"></div>
        <div class="bee1"></div>
        <div class="bee2"></div>
        <div class="bee3"></div>
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
    width: 1520px;
    height: 60px;
    border: 1px solid rgb(0, 0, 0);
    background-color: rgb(255, 255, 255);

    p {
        font-size: 20px;
        text-align: center;
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
    width: 300px;
    height: 200px;
    border: 1px solid rgb(0, 0, 0);
    display: flex;
    flex-direction: column;
    margin-top: 15px;
    margin-left: 300px;

    .team {
        width: 300px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        padding-top: 10px;
    }

    .team1 {
        width: 300px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        padding-top: 10px;
    }

    .team2 {
        width: 300px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);

        padding-top: 10px;
    }

    .team3 {
        width: 300px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);

        padding-top: 10px;
    }

    .team4 {
        width: 300px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        padding-top: 10px;
    }
}

.Group13 {
    width: 400px;
    height: 200px;
    border: 1px solid rgb(0, 0, 0);
    display: flex;
    flex-direction: column;
    margin-top: 20px;
    margin-left: 300px;

    .area {
        width: 400px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        text-align: center;
        padding-top: 20px;
    }

    .area1 {
        width: 400px;
        height: 140px;
        border: 1px solid rgb(0, 0, 0);


        .charger {
            resize: none;
        }
    }
}

.Group12 {
    width: 450px;
    height: 200px;
    border: 1px solid rgb(0, 0, 0);
    margin-top: 20px;
    margin-left: 300px;

    .bee {
        width: 450px;
        height: 200px;
    }
}
</style>
