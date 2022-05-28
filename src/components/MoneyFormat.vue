<template>
    <div class="money">
      <h1>{{ msg }}</h1>
      <p>1日圓 = 0.23台幣 ， 1美金 = 29.62台幣</p>
      <div class="currancy">
        <div class="twd">
          <input type="text" name="" id="twd" v-model="twd" required>
          <div class="underline"></div>
          <label for="twd">台幣:</label>
        </div>
        <div class="jpy">
          <input type="text" name="" id="jpy" v-model="jpy" required>
          <div class="underline"></div>
          <label for="jpy">日圓:</label>
        </div>
        <div class="usd">
          <input type="text" name="" id="usd" v-model="usd" required>
          <div class="underline"></div>
          <label for="usd">美金:</label>
        </div>
      </div>
    </div>
</template>

<style lang="scss">
  .money {
      width: 60%;
      height: 80%;
      font-size: 15px;
      font-weight: 400;
      // background-color: coral;
      color: white;
      margin: 0 auto;
      padding: 10px;
      border-radius: 8px;
      h1 {
          margin: 20px auto;
      }
      .currancy {
        text-align: left;
        margin: 0 auto;
        width: 45%;
        height: 45%;
        padding: 5% 36%;
        .twd,.jpy,.usd{
          height: 40px;
          width: 100%;
          margin: 30px auto 10px;
          position: relative;

          input {
            width: 60%;
            height: 30px;
            font-size: 18px;
            border: none;
            outline: none;
            border-bottom: 2px solid black;
            background-color: #929191;
            // color: white;

            &:focus ~ label,
            &:valid ~ label {
              transform: translateY(-30px);
            }
          }
          label {
            display: block;
            color:black;
            font-size: 18px;
            font-weight: 900;
            position: absolute;
            bottom: 10px;
            left: 0;
            pointer-events: none;
            transition: all 0.3 ease;
          }
        }
        .underline {
          position: absolute;
          bottom: 6px;
          height: 2px;
          width: 61%;

          &::before {
            position: absolute;
            content: "";
            height: 100%;
            width: 100%;
            background: white;
            transform: scaleX(0);
            transition: transform 0.3s ease;
          }
        }
        input:focus ~ .underline::before,
        input:valid ~ .underline::before {
          transform: scaleX(1);
        }
      }
  }
</style>

<script>
export default {
  name: 'MoneyFormat',
  data: () => ({
    twd: ''
  }),
  computed: {
    jpy: {
      get () {
        return Number.parseFloat(Number(this.twd) / 0.23).toFixed(3)
      },
      set (val) {
        this.twd = Number.parseFloat(Number(val) * 0.23).toFixed(3)
      }
    },
    usd: {
      get () {
        return Number.parseFloat(Number(this.twd) / 29.62).toFixed(3)
      },
      set (val) {
        this.twd = Number.parseFloat(Number(val) * 29.62).toFixed(3)
      }
    }
  },
  props: {
    msg: String
  }
}
</script>
