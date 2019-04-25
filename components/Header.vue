<template>
  <v-bottom-nav
      :value="true"
      fixed
      color="#fff"
    >
      <v-btn
        color="orange"
        flat
        value="recent"
        to="/profile"
      >
        <span>Profile</span>
        <v-icon>account_box</v-icon>
      </v-btn>

      <v-btn
        color="orange"
        flat
        value="quotes"
        to="/quotes/rindu"
      >
        <span>Quotes</span>
        <v-icon>format_quote</v-icon>
      </v-btn>

      <v-btn
        color="orange"
        flat
        value="news"
        to="/news"
      >
        <span>News</span>
        <v-icon>format_align_left</v-icon>
      </v-btn>

      <v-btn
        color="orange"
        flat
        value="signout"
        to="/"
      >
        <span>Sign Out</span>
        <v-icon>logout</v-icon>
      </v-btn>
    </v-bottom-nav>
</template>
