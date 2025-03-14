<script setup></script>

<template>
  <div class="card-container">
    <div class="img-container"><img src="" alt="" /></div>
    <div class="info-section">
      <div class="company-info">
        <h3>company name</h3>
        <span>new</span>
        <span>featured</span>
      </div>
      <h3>Jr front end developer</h3>
      <div class="date-container">
        <span>date</span>
        <span>Full time</span>
        <span>World Wide</span>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
$secondary-color: #83afc0;
.card-container {
  background-color: rgb(150, 167, 212);
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background-color: $secondary-color;
  width: 50%;
  margin: auto;
}
</style>
