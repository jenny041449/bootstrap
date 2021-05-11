<template>
  <div class="helloword">
    <section id="ani0">
      <img
        src="../assets/quien.svg"
        alt=""
        srcset=""
        id="quien"
        class="quien"
      />
      <h1 class="title">歡迎光臨-動畫書</h1>
    </section>
  
    <section class="stars two" id="two">
      <img
        src="../assets/flower.png"
        alt=""
        srcset=""
        class="flower"
        id="flower"
      />
      <img
        src="../assets/images.jpg"
        alt=""
        srcset=""
        class="twobg"
        id="twobg"
      />
    </section>

    <section>
      <h1 class="title">bootstrap練習</h1>
      <b-container fluid class="p-4 bg-dark">
        <b-row>
          <b-col>
            <b-img
              class="cardImg"
              thumbnail
              fluid
              src="https://picsum.photos/250/250/?image=54"
              alt="Image 1"
            ></b-img>
          </b-col>
          <b-col>
            <b-img
              thumbnail
              class="cardImg"
              fluid
              src="https://picsum.photos/250/250/?image=58"
              alt="Image 2"
            ></b-img>
          </b-col>
          <b-col>
            <b-img
              thumbnail
              class="cardImg"
              fluid
              src="https://picsum.photos/250/250/?image=59"
              alt="Image 3"
            ></b-img>
          </b-col>
        </b-row>
      </b-container>
    </section>
    <!-- form -->

    <section class="form">
      <h1>bootstrap表單</h1>
      <div>
        <b-form @submit="onSubmit" @reset="onReset" v-if="show2">
          <b-form-group
            id="input-group-1"
            label="Email address:"
            label-for="input-1"
            description="We'll never share your email with anyone else."
          >
            <b-form-input
              id="input-1"
              v-model="form.email"
              type="email"
              placeholder="Enter email"
              required
            ></b-form-input>
          </b-form-group>

          <b-form-group
            id="input-group-2"
            label="Your Name:"
            label-for="input-2"
          >
            <b-form-input
              id="input-2"
              v-model="form.name"
              placeholder="Enter name"
              required
            ></b-form-input>
          </b-form-group>

          <b-form-group id="input-group-3" label="Food:" label-for="input-3">
            <b-form-select
              id="input-3"
              v-model="form.food"
              :options="foods"
              required
            ></b-form-select>
          </b-form-group>

          <b-form-group id="input-group-4" v-slot="{ ariaDescribedby }">
            <b-form-checkbox-group
              v-model="form.checked"
              id="checkboxes-4"
              :aria-describedby="ariaDescribedby"
            >
              <b-form-checkbox value="me">Check me out</b-form-checkbox>
              <b-form-checkbox value="that">Check that out</b-form-checkbox>
            </b-form-checkbox-group>
          </b-form-group>

          <b-button type="submit" variant="primary">Submit</b-button>
          <b-button type="reset" variant="danger">Reset</b-button>
        </b-form>
        <b-card class="mt-3" header="Form Data Result">
          <pre class="m-0">{{ form }}</pre>
        </b-card>
      </div>
    </section>
  </div>
</template>
<script>
export default {
  data() {
    return {
      form: {
        email: "",
        name: "",
        food: null,
        checked: [],
      },
      foods: [
        { text: "Select One", value: null },
        "Carrots",
        "Beans",
        "Tomatoes",
        "Corn",
      ],
      show2: true,
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
      alert(JSON.stringify(this.form));
    },
    onReset(event) {
      event.preventDefault();
      // Reset our form values
      this.form.email = "";
      this.form.name = "";
      this.form.food = null;
      this.form.checked = [];
      // Trick to reset/clear native browser form validation state
      this.show2 = false;
      this.$nextTick(() => {
        this.show2 = true;
      });
    },
  },
};
// <script>
function getScrollTop() {
  var scrollTop = 0;
  if (document.documentElement && document.documentElement.scrollTop) {
    scrollTop = document.documentElement.scrollTop;
  } else if (document.body) {
    scrollTop = document.body.scrollTop;
  }
  return scrollTop;
}

window.addEventListener("scroll", function () {
  let scrolltop = getScrollTop();
  //  圖片上200就動
  let twobg = document.querySelector("#two").offsetTop - 200;
  let twoHeight = document.querySelector("#two").clientHeight;
  // 實際到圖片底
  let height = twoHeight + twobg;
  // console.log(scrolltop+" "+twobg+" "+height)
  // 櫻花飄動
  if (scrolltop > twobg && height > scrolltop) {
    let sub = -200 + scrolltop - twobg;
    document.getElementById("flower").style.top = sub + "px";
  }
});
// 走路
// let mouse=document.getElementsByClassName("mouse");
// for(let i=0;i<mouse.length;i++){
//  window.setTimeout(function(){

//  }, 2000);
// }
</script>
<style>
.bannerCake{
  padding: 20px;
  width: 100%;
}
.helloword section {
  margin-bottom: 50px ;
  min-height: 500px;
}
.helloword .backLoad {
  visibility: hidden;
}
.helloword .background { 
  overflow: hidden;
  background: url("../assets/backLoad.png");
}

.helloword .cardImg {
  overflow: hidden;
  transition: all 1s ease;
  transform-style: preserve-3d;
}
.helloword .cardImg:hover {
  transform: rotateY(180deg);
}

.helloword .title {
  color: white;
}
.helloword .form {
  background: white;
}
.helloword .form input {
  margin: auto;
  max-width: 500px;
}
.helloword {
  height: 3000px;
  background: url("../assets/stars.jpg") repeat;
  background-attachment: fixed;
}
.helloword .stars,
.helloword .bridge {
  position: relative;
  overflow: hidden;
}
.helloword .flower {
  position: absolute;
  top: -200px;
  left: 50%;
  transform: translate(-50%, 0);
}
.helloword .twobg {
  border: rgb(255, 229, 208) 10px solid;
}
.helloword .mouse {
  display: none;
  animation: 2s showrun forwards infinite;
}

.helloword .quien {
  margin: 30px 0;
  height: 300px;
  transform: translateY(-100%);
  position: relative;
  z-index: 1;
  animation: 1s translateFade 1 forwards, 2s scaleFade forwards infinite;
}
@keyframes translateFade {
  to {
    transform: translateY(0);
  }
}
@keyframes scaleFade {
  form {
    transform: scale(1);
  }
  to {
    transform: scale(1.1);
  }
}
.helloword .stars img {
  object-fit: cover;
  width: 100%;
  max-width: 800px;
  min-height: 500px;
  width: 100%;
  /* background: url('../assets/images.jpg'); */
}
</style>
