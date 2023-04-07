<template>
    <v-app>
        <v-app-bar app color="indigo" dark>
            <v-toolbar-title>{{ en_name }}</v-toolbar-title>
        </v-app-bar>

        <v-main>
            <v-container fluid>
                <v-row>
                    <v-col cols="12" md="4">
                        <v-card class="profile-card">
                            <v-img :src="avatar" :alt="zh_name" class="mx-auto"></v-img>
                            <v-card-text>
                                <div class="text-center">
                                    <h2>{{ zh_name }}</h2>
                                    <h2>{{ en_name }}</h2>
                                    <h4>{{ education }}</h4>
                                </div>
                                <div class="mt-5">
                                    <h3>Products:</h3>
                                    <ul>
                                        <li>{{ product }}</li>
                                    </ul>
                                </div>
                            </v-card-text>
                        </v-card>
                    </v-col>
                    <v-col cols="12" md="8">
                        <v-card class="about-card">
                            <v-card-title>
                                <h2>About Me</h2>
                            </v-card-title>
                            <v-card-text>
                                <p>I'm a developer who loves creating innovative products. I have a passion for building user-friendly and intuitive applications that improve people's lives.</p>
                                <p>My latest product is <a :href="productUrl" target="_blank">{{ product }}</a>, which I developed independently.</p>
                                <p>When I'm not coding, I enjoy spending time outdoors and exploring new places.</p>
                            </v-card-text>
                        </v-card>
                    </v-col>
                </v-row>
            </v-container>
        </v-main>
    </v-app>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import {en} from "vuetify/locale";

export default defineComponent({
    name: 'PersonalWebsite',
    computed: {
        en() {
            return en
        }
    },
    data() {
        return {
            zh_name: '王童',
            en_name: 'Tong Wang',
            avatar: 'https://wangtong15.oss-cn-beijing.aliyuncs.com/icon/avatar.jpeg',
            education: 'graduated from the Department of Electronic Engineering at Tsinghua University with a Bachelor\'s and Master\'s degree.',
            product: '散弹',
            productUrl: 'https://www.sandanapp.com'
        };
    },
    mounted() {
        document.title = this.en_name;
    }
});
</script>

<style lang="scss" scoped>
.profile-card {
    margin-top: 50px;
    max-width: 400px;
    margin-left: auto;
    margin-right: auto;

    img {
        max-width: 100%;
    }

    h2 {
        margin-top: 20px;
    }

    h4 {
        margin-top: 10px;
    }
}

.about-card {
    margin-top: 50px;
    margin-left: auto;
    margin-right: auto;
    max-width: 800px;

    h2 {
        margin-bottom: 20px;
    }

    p {
        line-height: 1.5;
        font-size: 18px;
        margin-bottom: 20px;

        a {
            color: #1976d2;
            text-decoration: none;
            font-weight: 500;

            &:hover {
                text-decoration: underline;
            }
        }
    }
}
</style>
