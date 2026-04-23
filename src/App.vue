<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios';

// 定義響應式變數來儲存數據
const dataList = ref([]);
const loading = ref(true);
const error = ref(null);

const fetchData = async () => {
    try {
        const response = await axios.get('https://nct.hosinoeiji.workers.dev/api/map-data');
        dataList.value = response.data; // Axios 會自動解析 JSON
    } catch (err) {
        error.value = "獲取數據失敗：" + err.message;
    } finally {
        loading.value = false;
    }
};

onMounted(() => {
    fetchData();
});
</script>

<template>
    <div class="body">
        <h1>NO CONVERSION THERAPY</h1>
        <p v-if="loading">載入中...</p>
        <p v-else-if="error">{{ error }}</p>
        <p>上一次數據更新：{{ dataList.last_synced }}</p>
        <div id="statisc">
            <h2>統計數據</h2>
            <span class="div">受害者平均年齡：{{ dataList.avg_age }}歲</span>
            <span class="div">收到表單數量：{{ dataList.formNum }}</span>
            <span class="div">已標記戒網癮學校：{{ dataList.schoolNum }}</span>
        </div>
        <h2>詳細信息</h2>
        <div id="data" v-for="(item, index) in dataList.data" :key="index">
            <div class="div schoolData">
                <h3>{{ item.name }}</h3>
                <div>
                    <p>校長：{{ item.HMaster }}</p>
                    <p>省份：{{ item.province }}</p>
                    <p>城市：{{ item.prov }}</p>
                    <p>學校地址：{{ item.addr }}</p>
                    <p>受害者經歷：{{ item.experience }}</p>
                    <p>機構醜聞：{{ item.scandal }}</p>
                    <p>機構聯係方式：{{ item.contact }}</p>
                    <p>其他補充：{{ item.else }}</p>
                    <p>表單類型：{{ item.inputType }}</p>

                </div>
            </div>
        </div>
    </div>
</template>


<style scoped>
#statisc{
    display: flex;
    flex-direction: column;
}
#statisc .div{
    margin: 10px auto;
}
#data{
    display: flex;
    justify-content: center;
}
#data .schoolData{
    width: 100%;
    margin: 10px 0;
}
.body{
    width: 80%;
    margin: 0 auto;
}
</style>
