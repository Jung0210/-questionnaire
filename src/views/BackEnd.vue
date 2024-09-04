<script>
export default {
    data() {
        return {
            searchArea: {
                quizName: "",
                startDate: "",
                endDate: "",
            },
            quizList: [],
            selectedQuizIds: []
        };
    },
    methods: {
        goToNextPage() {
            // sessionStorage.setItem('quiz', JSON.stringify({
            //     name: "",
            //     description: "",
            //     startDate: "",
            //     endDate: "",
            //     published: false,
            //     quesList: []
            // }));
            sessionStorage.clear();
            // 使用 Vue Router 的 push 方法導航到 /next 頁面
            this.$router.push('/BackEndInsidePage');
        },
        async search() {
            await this.saveData();
        },

        async saveData() {
            try {
                const response = await fetch('http://localhost:8080/quiz/search', { // 替換成你的後端API地址
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify(this.searchArea), // 將this.data轉成JSON字串發送
                });
                if (response.ok) {
                    console.log('數據保存成功！');
                    // 處理成功響應（例如，顯示成功消息）
                    console.log(response);
                    const data = await response.json(); // 解析返回的 JSON 數據
                    this.quizList = data.quizResList
                    console.log('返回的數據:', data.quizResList);
                    this.quizList.forEach(item => {
                        item.state = this.determineSituation(item.startDate, item.endDate, item.published)
                    })

                } else {
                    console.error('保存數據失敗。');
                    // 處理失敗響應（例如，顯示錯誤消息）
                }
            } catch (error) {
                console.error('發生錯誤：', error);
                // 處理網路或其他錯誤
            }
            this.back()
        },
        determineSituation(startDate, endDate, published) {
            if (!published) {
                return '未開放'
            }
            const now = new Date();
            const start = new Date(startDate);
            const end = new Date(endDate);
            if (now < start) {
                return '尚未開始';
            } else if (now >= start && now <= end) {
                return '開放中';
            } else {
                return '已结束';
            }
        },
        editQuiz(item) {
            // 将问卷数据存储到 Session Storage
            sessionStorage.setItem('quizData', JSON.stringify({
                id: item.id,
                name: item.name,
                description: item.description,
                startDate: item.startDate,
                endDate: item.endDate,
                published: item.published,
                quesList: item.quesList
            }));
            // sessionStorage.getItem('quizData')
            console.log(sessionStorage.getItem('quizData'));

            this.$router.push('/BackEndInsidePage');
        },


        async saveAndPublish() {
            this.data.published = true; // 添加一個標記或屬性表示發布
            await this.saveData();
        },
        back() {
            // 使用 Vue Router 的 push 方法導航到 /next 頁面

            this.$router.push('/BackEnd');

        },

        deleteSelected() {
            console.log(this.selectedQuizIds);

            if (this.selectedQuizIds.length === 0) {
                alert('請選擇要刪除的項目');
                return;
            }
            const confirmed = confirm('確定要刪除選中的項目嗎？');
            if (confirmed) {
                // 發送刪除請求
                fetch('http://localhost:8080/quiz/delete', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify({ quizIdList: this.selectedQuizIds }),
                })
                    .then(response => {
                        if (response.ok) {
                            console.log('刪除成功！');
                            // 更新列表
                            this.quizList = this.quizList.filter(item => !this.selectedQuizIds.includes(item.id));
                            this.selectedQuizIds = []; // 清空已選中的id
                        } else {
                            console.error('刪除失敗。');
                        }
                    })
                    .catch(error => {
                        console.error('發生錯誤：', error);
                    });

            }
        }
    }
}
</script>

<template>
    <div class="searchArea">
        <div class="enter">
            <p class="tree">問卷名稱:</p>
            <input v-model="searchArea.quizName" type="word" name="myfield" id="">
        </div>
        <div class="time">
            <p>統計時間:</p>
            <input v-model="searchArea.startDate" type="date" id="bookdate" name="">
            <p>到</p>
            <input v-model="searchArea.endDate" type="date" id="bookdate" name="">
            <button @click="search" class="press">搜尋</button>
        </div>
    </div>
    <div class="star">
        <div class="star1">
            <i class="fa-solid fa-trash" @click="deleteSelected" style="cursor: pointer;"></i>
        </div>
        <div class="star2">
            <i class="fa-solid fa-plus" @click="goToNextPage" style="cursor: pointer;"></i>
            <!-- style="cursor: pointer 它會把滑鼠游標變成手的形狀 -->
        </div>
    </div>
    <div class="Group18">
        <table class="box">
            <tr>
                <td> </td>
                <td> 編號 </td>
                <td> 名稱 </td>
                <td> 狀態 </td>
                <td> 開始時間 </td>
                <td> 結束時間 </td>
                <td> 結果 </td>
            </tr>
            <tr v-for="item in this.quizList" :key="item.id">
                <!-- v-bind是會把裡面的東西設為變數 -->
                <td><input type="checkbox" v-model="selectedQuizIds" :id="item.id" :value="item.id"></td>

                <td>{{ item.id }}</td>
                <td>
                    <a @click="editQuiz(item)">{{ item.name }}</a>
                </td>
                <!-- <td v-if="item.published">已發布</td>
                <td v-if="!item.published">未發布</td> -->
                <td>{{ item.state }}</td>
                <td>{{ item.startDate }}</td>
                <td>{{ item.endDate }}</td>
                <td>
                    <RouterLink :to="{ name: 'StatisticPage', params: { id: item.id } }">{{ item.result }}</RouterLink>
                </td>
            </tr>
        </table>
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
    // border: 1px solid rgb(0, 0, 0);
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    background-color: rgb(255, 248, 214);

    .enter {
        width: 500px;
        height: 60px;
        // border: 1px solid rgb(0, 0, 0);
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
        width: 500px;
        height: 60px;
        // border: 1px solid rgb(0, 0, 0);
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

.star {
    width: 150px;
    height: 50px;
    // border: 1px solid rgb(0, 0, 0);
    display: flex;
    justify-content: space-evenly;
    margin-top: 30px;
    margin-left: 500px;

    .star1 {
        width: 60px;
        height: 50px;
        // border: 1px solid rgb(0, 0, 0);
        font-size: 40px;
        text-align: center;
    }

    .star2 {
        width: 60px;
        height: 50px;
        // border: 1px solid rgb(0, 0, 0);
        font-size: 40px;
        text-align: center;
    }
}

.Group18 {
    width: 600px;
    // height: 300px;
    // border: 1px solid rgb(0, 0, 0);
    margin-top: 30px;
    margin-left: 450px;


    .box {
        width: 600px;
        // height: 300px;
        // border: 1px solid rgb(0, 0, 0);
        background-color: rgba(251, 255, 227, 0.995);
        text-align: center;
    }
}

.page {
    width: 714px;
    height: 28px;
    // border: 1px solid rgb(0, 0, 0);
    display: flex;
    margin-left: 380px;
    margin-top: 60px;
    padding-left: 200px;
}
</style>
