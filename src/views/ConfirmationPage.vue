<script>
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
            data: {},
            // questions: [],// 存儲所有問題

            editingIndex: null, // 記錄正在編輯的問題的索引

            questionList: [],

            question: {
                id: '',
                qu: '',
                type: '',
                necessary: false,
                options: '',
            }

        };
    },
    methods: {
        async saveData() {
            try {
                this.data.quesList.forEach(item => {
                    item.options = item.options.join(";")
                })
                console.log(this.data)
                const response = await fetch('http://localhost:8080/quiz/create', { // 替換成你的後端api位址
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify(this.data), // 將this.data轉成JSON字串發送
                });
                if (response.ok) {
                    console.log('数据保存成功！');
                    // 處理成功響應（例如，顯示成功消息）
                } else {
                    console.error('保存数据失败。');
                    // 處理失敗響應（例如，顯示錯誤消息）
                }
            } catch (error) {
                console.error('发生错误：', error);
                // 處理網路或其他錯誤
            }
            this.back()
        },
        async saveAndPublish() {
            this.data.published = true; // 
            await this.saveData();
        },
        back() {
            // 使用 Vue Router 的 push 方法導航到 /next 頁面
            this.$router.push('/BackEnd');
        }
    },

    mounted() {
        const data = sessionStorage.getItem('quizData')
        console.log(data)
        if (data) {
            this.data = JSON.parse(data)
            this.data.quesList.forEach(item => {
                item.options = item.options.split(";")
            })
        }
        console.log(data)

    }
}
</script>

<template>
    <div class="first">
        <p>{{ data.name }}</p>
    </div>

    <div class="shape">
        <p> {{ data.description }}</p>
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
                <input v-model="question.qu" type="one" disabled>
            </div>
            <div class="line1">
                <input type="one" disabled>
            </div>
            <div class="line2">
                <input type="one" disabled>
            </div>
            <div class="line3">
                <input type="one" disabled>
            </div>
        </div>
    </div>

    <div class="Group15">

        <div class="team" v-for="(item, index) in this.data.quesList" :key="index">
            <p>{{ item.qu }}</p>

            <div v-if="item.necessary">(必填)</div>


            <div v-for=" (option, i) in item.options" :key="i">

                <div v-if="item.type === 'single'" class="team1">
                    <!---單選題,使用radio--->
                    <input type="radio" :name="question">
                    {{ option }}
                </div>
                <!-- v-for="(option,i) in this item.options" :key="i" -->

                <div v-if="item.type === 'multiple'" class="team1">
                    <!-- 多選題，使用 checkbox -->
                    <input type="checkbox">
                    {{ option }}
                </div>

                <div v-if="item.type === 'short'" class="team1">
                    <!-- 短述題 -->
                    <textarea></textarea>
                    {{}}
                </div>
            </div>
        </div>
    </div>
    <div class="Group10">
        <div class="egg1">
            <button @click="saveData" class="Cancel">僅儲存</button>
        </div>
        <div class="egg2">
            <button class="send">儲存並發布</button>
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
    // border: 1px solid rgb(0, 0, 0);
    margin-top: 20px;
    display: flex;
    margin-left: 300px;

    .chocolate {
        width: 350px;
        height: 198px;
        // border: 1px solid rgb(0, 0, 0);
        display: flex;
        flex-direction: column;
        justify-content: space-around;

        .box {
            width: 349px;
            height: 40px;
            // border: 1px solid rgb(0, 0, 0);
            // display: flex;
            // padding-top: 10px;
            font-size: 20px;
            padding-top: 10px;
            text-align: center;
        }

        .box1 {
            width: 349px;
            height: 40px;
            // border: 1px solid rgb(0, 0, 0);
            padding-top: 10px;
            font-size: 20px;
            text-align: center;
        }

        .box2 {
            width: 349px;
            height: 40px;
            // border: 1px solid rgb(0, 0, 0);
            font-size: 20px;
            padding-top: 10px;
            text-align: center;
        }

        .box3 {
            width: 349px;
            height: 40px;
            // border: 1px solid rgb(0, 0, 0);
            font-size: 20px;
            text-align: center;
            // justify-content: center;
            padding-top: 10px;
        }
    }

    .enter {
        width: 1000px;
        height: 200px;
        // border: 1px solid rgb(0, 0, 0);
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
    width: 500px;
    // height: 250px;
    // border: 1px solid rgb(0, 0, 0);
    margin-top: 30px;
    margin-left: 300px;
    // display: flex;
    // flex-direction: column;
    // text-align: left;

    .team {
        width: 500px;
        // height: 50px;
        // border: 1px solid rgb(0, 0, 0);
        padding-top: 50px;
        // text-align: center;
        justify-content: flex-start;



        input {
            width: 20px;
            display: flex;
            flex-direction: column;
            // text-align: left;

        }
    }

    .team1 {
        width: 500px;

        border: 1px solid rgb(0, 0, 0);
        // padding-top: 10px;
        // justify-content: center;
        display: flex;
        margin-top: auto;

        p {
            text-align: center;
        }

    }
}

.Group13 {
    width: 400px;
    height: 200px;
    border: 1px solid rgb(0, 0, 0);
    display: flex;
    flex-direction: column;
    margin-top: 100px;
    margin-left: 300px;

    .area {
        width: 800px;
        height: 40px;
        text-align: left;

        .input {
            width: 800px;
            height: 60px;
        }


        p {
            font-size: 18px;
            text-align: left;
        }
    }

    .area1 {
        width: 400px;
        height: 190px;
        padding-top: 10px;
        // border: 1px solid rgb(0, 0, 0);
        position: relative;
        display: flex;
        justify-content: space-between;

        textarea {
            width: 385px;
            height: 150px;
            border: 1px solid rgb(0, 0, 0);
            resize: none;
            position: absolute;
            left: 7px;
            top: 9px;

        }
    }
}

// .Group12 {
//     width: 500px;
//     height: 250px;
//     border: 1px solid rgb(0, 0, 0);
//     margin-top: 30px;
//     margin-left: 300px;
//     display: flex;
//     // justify-content: space-around;
//     flex-direction: column;
//     text-align: left;

//     // .bee {
//     //     width: 450px;
//     //     height: 50px;
//     //     border: 1px solid rgb(0, 0, 0);
//     //     padding-top: 8px;

//     //     input {
//     //         width: 399px;
//     //         height: 35px;
//     //     }
//     // }

//     // .bee1 {
//     //     width: 450px;
//     //     height: 50px;
//     //     border: 1px solid rgb(0, 0, 0);
//     //     justify-content: left;
//     //     // display: flex;



//     //     input {
//     //         width: 40px;
//     //         height: 20px;
//     //         border: 1px solid rgb(0, 0, 0);
//     //         margin-top: 10px;
//     //     }

//     // }

//     // .bee2 {
//     //     width: 450px;
//     //     height: 50px;
//     //     border: 1px solid rgb(0, 0, 0);
//     //     display: flex;
//     //     justify-content: space-between;
//     //     align-items: center;

//     //     input {
//     //         width: 40px;
//     //         height: 20px;
//     //         border: 1px solid rgb(0, 0, 0);
//     //         margin-top: 10px;
//     //     }
//     // }

//     // .bee3 {
//     //     width: 450px;
//     //     height: 50px;
//     //     border: 1px solid rgb(0, 0, 0);
//     //     display: flex;
//     //     justify-content: space-between;
//     //     align-items: center;

//     //     input {
//     //         width: 40px;
//     //         height: 20px;
//     //         border: 1px solid rgb(0, 0, 0);
//     //         margin-top: 10px;
//     //     }
//     // }

//     // .bee4 {
//     //     width: 450px;
//     //     height: 50px;
//     //     border: 1px solid rgb(0, 0, 0);
//     //     display: flex;
//     //     justify-content: space-between;
//     //     align-items: center;

//     //     input {
//     //         width: 40px;
//     //         height: 20px;
//     //         border: 1px solid rgb(0, 0, 0);
//     //         margin-top: 10px;
//     //     }

//     // }

// }

.Group10 {
    width: 400px;
    height: 50px;
    // border: 1px solid rgb(0, 0, 0);
    margin-top: 25px;
    margin-left: 1000px;
    display: flex;

    .egg1 {
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

    .egg2 {
        width: 200px;
        height: 50px;
        // border: 1px solid rgb(0, 0, 0);
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
