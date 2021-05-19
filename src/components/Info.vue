<template>
  <div id="info-container">
    <div id="instructions"><p>Scroll below to advance the story!</p></div>
    <div id="info-track">
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="1">
          <p>
            When it comes to budgetary spending, there is one golden rule: you
            spend more, you get more. This holds true for most budgets,
            including those of our representatives in Congress. Considering that
            our tax dollars are what these budgets consist of, we might want to
            know how much our representatives are spending, and on what.
          </p>
          <p>
            On the other hand, the United States is a purposefully large
            republic with a wide range of cultural differences and a variety of
            needs—so
            <b
              >to what extent does geography factor into our representatives’
              budgetary spending habits?</b
            >
            Let's find out!
          </p>
        </div>
      </section>
      <section>
        <div id="waypoint" class="info-box" data-step="2">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua. Cras
          semper auctor neque vitae tempus quam pellentesque nec nam. Eu feugiat
          pretium nibh ipsum consequat. Mi quis hendrerit dolor magna eget est
          lorem ipsum. Dignissim cras tincidunt lobortis feugiat. Auctor eu
          augue ut lectus arcu bibendum at varius. Donec et odio pellentesque
          diam volutpat commodo sed egestas egestas. Venenatis a condimentum
          vitae sapien pellentesque habitant morbi tristique. Cras pulvinar
          mattis nunc sed blandit libero volutpat sed. Tincidunt lobortis
          feugiat vivamus at. Nunc aliquet bibendum enim facilisis gravida
          neque.
        </div>
      </section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="3">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua. Elit eget
          gravida cum sociis natoque penatibus et magnis dis. Lacus vestibulum
          sed arcu non odio euismod lacinia. Urna duis convallis convallis
          tellus id interdum velit. Amet est placerat in egestas erat imperdiet.
          Turpis egestas maecenas pharetra convallis posuere morbi leo.
          Ullamcorper malesuada proin libero nunc consequat interdum. Elementum
          tempus egestas sed sed risus. Elit pellentesque habitant morbi
          tristique. Ornare suspendisse sed nisi lacus sed viverra tellus in.
          Sed id semper risus in.
        </div>
      </section>
      <section>
        <div class="info-box" data-step="4">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua. Quam
          pellentesque nec nam aliquam sem et tortor consequat id. Lacus sed
          viverra tellus in. Congue nisi vitae suscipit tellus mauris a diam
          maecenas sed. Egestas congue quisque egestas diam in arcu. Adipiscing
          enim eu turpis egestas pretium aenean pharetra. Tincidunt dui ut
          ornare lectus sit amet est. Sed vulputate odio ut enim blandit. Urna
          nunc id cursus metus aliquam eleifend mi in nulla. Sagittis eu
          volutpat odio facilisis. Turpis egestas sed tempus urna et pharetra.
        </div>
      </section>
      <section><div class="info-box" data-step="5">test</div></section>
      <section><div class="info-box" data-step="6">test</div></section>
      <section><div class="info-box" data-step="7">test</div></section>
      <section @wheel="$emit('stepcatcher', step)">
        <div class="info-box" data-step="8">test</div>
      </section>
      <section><div class="info-box" data-step="9">test</div></section>
      <section><div class="info-box" data-step="10">test</div></section>
      <section><div class="info-box" data-step="11">test</div></section>
      <section><div class="info-box" data-step="12">test</div></section>
      <section><div class="info-box" data-step="13">test</div></section>
    </div>
  </div>
</template>
<script>
import "intersection-observer";
import scrollama from "scrollama";
const scroller = scrollama();

export default {
  name: "Info",
  props: [],
  emits: ["stepcatcher"],
  data() {
    return {
      step: null,
    };
  },
  methods: {
    scroll: function () {
      console.log(this);
      scroller
        .setup({
          step: "#info-track section .info-box",
          debug: true,
          offset: 0.5,
        })
        .onStepEnter((response) => {
          this.step = response.index;
          console.log(this.step);
        });
    },
  },
  // updated(){

  // }
  mounted() {
    this.scroll();
  },
};
</script>
<style scoped>
#info-track {
  background-color: rgba(255, 255, 255, 0.38);
  scroll-behavior: smooth;
  overflow-y: scroll;
  scrollbar-width: none;
  height: 88vh;
  height: fit-content;
}

::-webkit-scrollbar {
  display: none;
}
.info-box {
  margin: 2vw;
  background-color: #1b2a36;
  padding: 3vw;
  border-radius: 28px;
  color: #fffbe6;
}

section {
  min-height: 100vh;
  padding: 10vw 5vh;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  box-sizing: border-box;
}
#instructions {
  background-color: #28c5d1;
  height: 8vh;
  position: fixed;
  width: 40%;
  /* margin: auto; */
  display: grid;
}
#instructions p {
  color: #1b2a36;
  z-index: 999;
  position: fixed;
  text-align: center;
  /* margin: auto; */
  justify-self: center;
}
</style>
