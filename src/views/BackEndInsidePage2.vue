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
                <div class="oval13">
                    <p>問題:</p>
                </div>
                <div class="oval14">
                    <input type="text">
                </div>
                <div class="oval15">
                    <select name="list" id="chose">
                        <option value="No1">單選題</option>
                        <option value="No2">複選題</option>
                    </select>
                </div>
                <div class="oval16">
                    <input type="checkbox" id="fill">
                    <label for="fill" class="fit">必填</label>
                </div>
            </div>
        </div>
        <div class="oval2">
            <div class="oval17">
                <div class="oval18">
                    <p>選項:</p>
                </div>
                <div class="oval19">
                    <p>(多個答案請以;分隔)</p>
                </div>
            </div>
            <div class="oval20">
                <textarea name="" id=""></textarea>
            </div>
            <div class="oval21">
                <button>加入</button>
            </div>
        </div>
        <div class="Group3">
            <div class="oval22">
                <i class="fa-regular fa-trash-can"></i>
            </div>
        </div>
        <div class="Group4">
            <div class="box1">
                <table class="box2">
                    <tr>
                        <td></td>
                        <td>編號</td>
                        <td>內容</td>
                        <td>問題種類</td>
                        <td> 必填</td>
                        <td>編輯</td>
                    </tr>
                    <tr>
                        <td><input type="checkbox"></td>
                        <td>#1</td>
                        <td> 請選取最喜歡的人 </td>
                        <td> 單選題</td>
                        <td> <input type="checkbox"> </td>
                        <td> 編輯 </td>
                    </tr>
                    <tr>
                        <td> <input type="checkbox" id=""> </td>
                        <td> #2</td>
                        <td> 請說明理由 </td>
                        <td> 短述題</td>
                        <td> <input type="checkbox"> </td>
                        <td> 編輯 </td>
                    </tr>
                    <tr>
                        <td> <input type="checkbox" id=""> </td>
                        <td> #3</td>
                        <td> 請選取在活動開始前有聽過 </td>
                        <td> 單選題</td>
                        <td> <input type="checkbox"> </td>
                        <td> 編輯 </td>
                    </tr>
                </table>
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
    height: 600px;
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


        .oval1 {
            width: 1100px;
            height: 100px;
            // border: 1px solid rgb(0, 0, 0);
            font-size: 30px;
            padding-right: 100px;
            display: flex;
            align-items: center;
            justify-content: space-around;



            .oval13 {
                width: 100px;
                height: 40px;
                border: 1px solid rgb(0, 0, 0);
                text-align: center;
            }

            .oval14 {
                width: 600px;
                height: 50px;
                border: 1px solid rgb(0, 0, 0);

                input {
                    width: 600px;
                    height: 50px;
                }
            }

            .oval15 {
                width: 100px;
                height: 40px;
                border: 1px solid rgb(0, 0, 0);

                #chose {
                    width: 100px;
                    height: 40px;
                    border: 1px solid rgb(0, 0, 0);
                    font-size: 25px;
                }
            }

            .oval16 {
                width: 80px;
                height: 40px;
                // border: 1px solid rgb(0, 0, 0);

                .fit {
                    font-size: 20px;
                }
            }
        }
    }

    .oval2 {
        width: 1000px;
        height: 200px;
        // border: 1px solid rgb(0, 0, 0);
        font-size: 30px;
        display: flex;
        flex-direction: column;
        position: relative;

        .oval17 {
            width: 600px;
            height: 50px;
            // border: 1px solid rgb(0, 0, 0);
            display: flex;
            justify-content: space-around;



            .oval18 {
                width: 100px;
                height: 40px;
                // border: 1px solid rgb(0, 0, 0);
                text-align: right;
                margin-right: 42px;
            }

            .oval19 {
                width: 190px;
                height: 30px;
                // border: 1px solid rgb(0, 0, 0);
                font-size: 20px;
                margin-right: 265px;
            }
        }
    }

    .oval20 {
        width: 700px;
        height: 150px;
        border: 1px solid rgb(0, 0, 0);
        display: flex;
        flex-direction: column;
        margin-left: 180px;

        textarea {
            width: 700px;
            height: 153px;
            resize: none;
        }
    }

    .oval21 {
        width: 80px;
        height: 50px;
        border: 1px solid rgb(0, 0, 0);
        display: flex;
        justify-content: end;
        margin-left: 910px;
        margin-top: -96px;


        button {
            width: 80px;
            height: 50px;
            font-size: 25px;
        }
    }

    .Group3 {
        width: 200px;
        height: 100px;
        // border: 1px solid rgb(0, 0, 0);
        display: flex;
        justify-content: center;
        padding-right: 60px;
        align-items: center;

        .oval22 {
            width: 100px;
            height: 50px;
            // border: 1px solid rgb(0, 0, 0);
            font-size: 40px;
            text-align: center;
        }
    }

    .Group4 {
        width: 1000px;
        height: 200px;
        border: 1px solid rgb(0, 0, 0);

        .box2 {
            width: 1000px;
            height: 200px;
            border: 1px solid rgb(0, 0, 0);
        }
    }
}
</style>