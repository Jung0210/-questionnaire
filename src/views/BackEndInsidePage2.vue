<script>
import axios from 'axios';
export default {
    data() {
        return {
            quid: 1,
            newQuestion: {
                text: '',
                type: "single",
                options: '',
                require: false,
            },
            isEdit: false,//boolean false是編輯
            data: [],
            // questions: [],// 存儲所有問題

            editingIndex: null, // 記錄正在編輯的問題的索引

            questionList: [],

            question: {
                quizId: 0,
                id: '',
                qu: '',
                type: '',
                necessary: false,
                options: '',
            },
            data2: {}

        };
    },
    mounted() {
        const data = sessionStorage.getItem('quiz')
        this.data2 = JSON.parse(sessionStorage.getItem('quizData'))
        console.log(data)
        console.log(this.data2)
        if (data) {
            this.data = JSON.parse(data)
        }
        console.log(data)
        console.log(this.data2);
        if (this.data2) {
            this.data2.quesList.forEach(item => {
                this.questionList.push(item);
            })
        }
        console.log(this.data2);
        // console.log(this.data)
        // const survey = JSON.parse(sessionStorage.getItem('question`'));
    },
    methods: {
        addQuestion() {
            const data3 = JSON.parse(sessionStorage.getItem('quizData'))
            // console.log(data3.id)
            if (this.question.qu) {
                if (this.question.type !== 'short' && !this.question.options) {
                    alert('請輸入選項');
                    return;
                }
                // this.question.quizId = data3.id
                this.question.id = this.questionList.length + 1
                this.questionList.push({ ...this.question });//把新增的問題增加到陣列裡
                //重置問題
                this.question.qu = '';
                this.question.type = 'single';
                this.question.options = '';
                this.question.necessary = false;
                this.quid++
            } else {
                alert('請輸入問題');
            }
        },
        // 設置編輯模式
        editQuestion(index) {
            this.isEdit = true;
            if (index >= 0 && index < this.questionList.length) {
                this.editingIndex = index;
                this.question = { ...this.questionList[index] };
            } else {
                alert('無效的問題索引');
            }
        },
        // 更新問題
        updateQuestion() {
            if (this.editingIndex !== null && this.question.qu) {
                this.questionList[this.editingIndex] = { ...this.question };
                this.resetNewQuestion();
                this.isEdit = false;
            }

        },
        // 重置問題填寫表單
        resetNewQuestion() {
            this.question = {
                quizId: this.data2.id,
                qu: '',
                type: 'single',
                options: '',
                necessary: false,
            };
            this.editingIndex = null;
        },
        // 刪除問題
        deleteQuestion(index) {
            this.questionList.splice(index, 1);
        },
        previewQuestions() {
            const data2 = JSON.parse(sessionStorage.getItem('quizData'))
            console.log(this.questionList)
            console.log(this.data2)
            // this.questionList.forEach(item => {
            //     this.data2.quesList.push(item)
            // })
            this.data.quesList = this.questionList
            console.log(data2)
            sessionStorage.setItem('quizData', JSON.stringify(this.data))
            this.$router.push({ name: 'ConfirmationPage' });
        },
        previousPage() {
            this.$router.push({ name: 'BackEndInsidePage' });
        }
    },

}
</script>

<template>
    <div class="Group0">
        <div class="circle1">
            <p>問卷</p>
        </div>
        <div class="circle2" :class="{ 'bgColor': this.$route.path == '/BackEndInsidePage2' }">
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
                    <input v-model="question.qu" type="text">
                </div>
                <div class="oval15">
                    <select v-model="question.type" name="" id="chose">
                        <option value="single">單選題</option>
                        <option value="multiple">複選題</option>
                        <option value="short">短述題</option>
                    </select>
                </div>
                <div class="oval16">
                    <input v-model="question.necessary" type="checkbox" id=" fill" />
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
                <textarea name="" id=" " v-model="question.options"></textarea>
            </div>
            <!-- <h1>{{ question }}</h1> -->
            <div class="oval21">
                <button @click="addQuestion" v-if="!isEdit">加入</button>
                <button @click="updateQuestion" v-if="isEdit">編輯</button>
            </div>
        </div>
        <div class="Group4">
            <div class="box1">
                <table class="box2">
                    <tr>

                        <td>編號</td>
                        <td>內容</td>
                        <td>問題種類</td>
                        <td> 必填</td>
                        <td>編輯</td>
                    </tr>
                    <tr v-for="(question, index) in questionList" :key="index">
                        <!-- <td><input type="checkbox" /></td> -->
                        <td>{{ index + 1 }}</td>
                        <td> {{ question.qu }}</td>
                        <td>{{ question.type }}</td>
                        <td> <input type="checkbox" :checked="question.necessary" disabled /> </td>
                        <td>
                            <a @click="editQuestion(index)">編輯</a>
                        </td>
                        <td><i class="fa-regular fa-trash-can" @click="deleteQuestion(index)"></i></td>
                    </tr>
                    <tr>
                        <td> <input type="checkbox" id=""> </td>
                        <td> </td>
                        <td> </td>
                        <td> </td>
                        <td> <input type="checkbox"> </td>
                        <td> </td>
                    </tr>
                    <tr>
                        <td> <input type="checkbox" id=""> </td>
                        <td> </td>
                        <td> </td>
                        <td> </td>
                        <td> <input type="checkbox"> </td>
                        <td> </td>
                    </tr>
                </table>
            </div>
        </div>
        <div class="end">
            <div class="line">
                <button @click="previousPage" class="pre">上一步</button>
            </div>
            <div class="lineright">
                <button @click="previewQuestions" class="send">送出</button>
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
    // border: 1px solid rgb(0, 0, 0);
    margin-left: 200px;
    display: flex;
    // justify-content: space-between;
    background-color: rgb(255, 252, 207);
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
    border-top-right-radius: 0px;
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
                // border: 1px solid rgb(0, 0, 0);
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
        width: 730px;
        height: 150px;
        // border: 1px solid rgb(0, 0, 0);
        display: flex;
        flex-direction: column;
        margin-left: 146px;

        textarea {
            width: 730px;
            height: 150px;
            resize: none;
        }
    }

    .oval21 {
        width: 80px;
        height: 50px;
        // border: 1px solid rgb(0, 0, 0);
        display: flex;
        justify-content: end;
        margin-left: 895px;
        margin-top: -96px;
        border-radius: 10px;


        button {
            width: 80px;
            height: 50px;
            font-size: 25px;
            border-radius: 10px;
        }

    }

    .oval22 {
        width: 80px;
        height: 50px;
        display: flex;
        margin-left: 895px;
        margin-top: 160px;

        button {
            width: 80px;
            height: 50px;
            font-size: 25px;
            border-radius: 10px;
        }
    }

    .Group3 {
        width: 150px;
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
        width: 735px;
        border: 0px solid rgb(0, 0, 0);
        margin-top: 95px;
        margin-left: 146px;
        margin-right: 500px;
        margin-bottom: 100px;


        .box2 {
            width: 700px;
            border: 1px solid rgb(0, 0, 0);
            margin-top: 0px;
            border-radius: 10px;
        }
    }

    .end {
        width: 600px;
        // border: 1px solid rgb(0, 0, 0);
        display: flex;
        margin-left: 205px;
        margin-right: 500px;
        margin-bottom: 100px;

        .line {
            width: 300px;
            height: 95px;
            display: flex;
            flex-direction: column;
            // border: 1px solid rgb(0, 0, 0);
            justify-content: center;
            align-items: center;

            .pre {
                width: 80px;
                height: 35px;
                font-size: 15px;
                padding: auto auto;
                border-radius: 10px;
            }
        }

        .lineright {
            width: 300px;
            height: 95px;
            display: flex;
            flex-direction: column;
            // border: 1px solid rgb(0, 0, 0);
            justify-content: center;
            align-items: center;

            .send {
                width: 80px;
                height: 35px;
                padding: auto auto; //兩個auto代表x軸和y軸
                font-size: 15px;
                text-align: center;
                border-radius: 10px;
            }
        }
    }
}
</style>