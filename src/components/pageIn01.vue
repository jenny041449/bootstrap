<template>
  <div class="back">
    <div class="list list1">歡</div>
    <div class="list list2">迎</div>
    <div class="list list3">光</div>
    <div class="list list4">臨</div>
    <div class="list list5">*</div>
  </div>
</template>
 
<style>
.back {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  background: rgb(250, 250, 250);

  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: space-evenly;
  font-size: 2em;

}

.back div {
  width: calc(20% - 20px);
  height: 100vh;
  background: rgb(142, 188, 196);
  transform: translateY(-100vh);
  display: flex;
  justify-content: center;
  align-items: center;
}

.list1 {
  height: 100vh;
  animation: data;
  animation-duration: 1s;
  animation-delay: 0s;
  animation-fill-mode: forwards;
}

.list2 {
  height: 100vh;
  animation: data;
  animation-duration: 1s;
  animation-delay: 2.2s;
  animation-fill-mode: forwards;
}

.list3 {
  height: 100vh;
  animation: data;
  animation-duration: 1s;
  animation-delay: 3.3s;
  animation-fill-mode: forwards;
}

.list4 {
  height: 100vh;
  animation: data;
  animation-duration: 1s;
  animation-delay: 4.3s;
  animation-fill-mode: forwards;
}

.list5 {
  height: 100vh;
  animation: data;
  animation-duration: 1s;
  animation-delay: 5.3s;
  animation-fill-mode: forwards;
}

@keyframes data {
  0% {
    transform: translateY(-100vh);
  }
  100% {
    transform: translateY(0);
  }
}
</style>