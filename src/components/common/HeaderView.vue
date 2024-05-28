<template>
    <v-app-bar color="headerBg">
        <v-btn @click="movePage('/politics')">Ecomo Automat</v-btn>
        <v-spacer></v-spacer>
        <v-card-text>
            <v-text-field
                v-model="searchKeyword"
                @keyup.enter="search"
                density="compact"
                variant="solo"
                label="Search keyword"
                append-inner-icon="mdi:magnify"
                single-line
                hide-details
            ></v-text-field>
        </v-card-text>
        <v-spacer></v-spacer>
        <v-btn icon="dark_mode" @click="toggleTheme" v-if="theme.current.value.dark"></v-btn>
        <v-btn icon="light_mode" @click="toggleTheme" v-else></v-btn>
        <div v-if="!profile">
            <v-btn
                icon="mdi:mdi-account-outline"
                @click="login"
                v-if="theme.current.value.dark"
            ></v-btn>
            <v-btn icon="mdi:mdi-account" @click="login" v-else></v-btn>
        </div>
        <div v-else>
            <v-menu open-on-hover>
                <template v-slot:activator="{ props }">
                    <v-btn>
                        <img
                            :src="profile.thumbnail_image"
                            alt="kakao_profile"
                            width="30"
                            height="30"
                            v-if="profile"
                            />
                    </v-btn>
                </template>
                <v-list>
                    <v-list-item v-for="(item, i) in profileMenu" :key="i">
                        <v-btn @click="movePage(item.url)">{{ item.title }}</v-btn>
                    </v-list-item>
                </v-list>
            </v-menu>
        </div>
    </v-app-bar>
</template>

<script>

</script>