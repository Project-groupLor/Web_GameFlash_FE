<template>
    <div class="container">
        <div class="row">
                <h2 class="text-center text-danger"> <i>Game Nổi Bật</i></h2>
            <template v-for="(v, k) in displayedGames" :key="k">
                <div class="col-lg-3 mt-3 d-flex">
                    <div class="card" style="background: linear-gradient(135deg, #2a2a3a 0%, #323248 100%); box-shadow: 0 8px 16px rgba(0,0,0,0.2); border: none;">
                        <div class="card-body text-center">
                            <img style="width: 200px; border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.15);" class="mb-2" :src="v.thumbnail" alt="" />
                            <h4 class="card-title" style="color: #ff6b6b;">{{ v.title }}</h4>
                           
                            <p class="text-start" style="color: #cccccc;">
                                <i>{{ v.description }}</i>
                            </p>
                        </div>
                        <div class="game-stats mb-2 d-flex justify-content-between" style="color: #ffd700;">
                                <span class="ms-2 ">⭐ {{ (Math.random() * 4 + 1).toFixed(1) }}</span>
                                <span class="me-2" style="color: #cccccc;">👥 {{ Math.floor(Math.random() * 9900 + 100) }} lượt chơi</span>
                         </div>
                        <div class="card-footer text-center" style="background: transparent; border-top: 1px solid rgba(255,255,255,0.1);">
                            
                            <button @click="playGame(v.id)" class="btn w-100" style="background-color: #ff6b6b; color: white; border: none; transition: all 0.3s ease;">Chơi Ngay</button>
                        </div>
                    </div>
                </div>
            </template>
        </div>
        <div class="row mt-4 mb-4" v-if="hasMoreGames">
            <div class="col-12 text-center">
                <button @click="loadMore" class="btn btn-success">Xem Thêm</button>
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";
export default {
    data() {
        return {
            listGame: [],
            currentPage: 1,
            itemsPerPage: 12
        };
    },
    computed: {
        displayedGames() {
            return this.listGame.slice(0, this.currentPage * this.itemsPerPage);
        },
        hasMoreGames() {
            return this.currentPage * this.itemsPerPage < this.listGame.length;
        }
    },
    mounted() {
        this.getListGame();
    },
    methods: {
        getListGame() {
            axios.get("http://127.0.0.1:8000/api/getdata").then((res) => {
                this.listGame = res.data.data;
            });
        },
        loadMore() {
            this.currentPage++;
        },
        playGame(id) {
            this.$router.push(`/game/${id}`);
        }
    },
};
</script>

<style scoped>
.btn-primary {
    background-color: #007bff;
    border-color: #007bff;
    padding: 10px 30px;
    font-size: 1.1rem;
    transition: all 0.3s ease;
}

.btn-primary:hover {
    background-color: #0056b3;
    border-color: #0056b3;
    transform: translateY(-2px);
}
</style>