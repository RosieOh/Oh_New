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
                icon="mdi"
            ></v-btn>

        </div>
    </v-app-bar>
    <div>
        
    </div>
</template>