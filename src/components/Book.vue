<template>
    <div>
      <h1>Book List</h1>
      <v-data-table :headers="bookHeaders" :items="books" class="elevation-1" />
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  // Book 테이블 헤더
  const bookHeaders = [
    { text: "Title", value: "title" },
    { text: "Author", value: "author" },
    { text: "Published Year", value: "year" },
  ];
  
  // Book 데이터
  const books = [
    { title: "The Great Gatsby", author: "F. Scott Fitzgerald", year: 1925 },
    { title: "To Kill a Mockingbird", author: "Harper Lee", year: 1960 },
    { title: "1984", author: "George Orwell", year: 1949 },
  ];
  </script>