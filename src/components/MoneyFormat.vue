<template>
    <div class="money">
      <h3>1日圓 = 0.23台幣 ， 1美金 = 29.62台幣</h3>
      <div class="currency">
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
      width: 100%;
      font-size: 15px;
      font-weight: 400;
      color: rgb(0, 0, 0);
      .currency {
        text-align: left;
        margin: 100px auto 0;
        max-width: 300px;
        .twd,.jpy,.usd{
          height: 40px;
          width: 100%;
          margin: 30px auto 10px;
          position: relative;

          input {
            width: 98%;
            height: 30px;
            font-size: 18px;
            border: none;
            outline: none;
            border-bottom: 2px solid #f7efef;
            background-color: #ffffff;
          }
          label {
            display: block;
            color:black;
            font-size: 18px;
            font-weight: 900;
            position: absolute;
            bottom: 45px;
            left: 0;
            pointer-events: none;
            transition: all 0.3 ease;
          }
        }
        .underline {
          position: absolute;
          bottom: 10px;
          height: 2px;
          width: 100%;

          &::before {
            position: absolute;
            content: "";
            height: 100%;
            width: 100%;
            background: #3f51b5;
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
  props: {
    msg: String
  },
  data: () => ({
    twd: ''
  }),
  computed: {
    jpy: {
      get () {
        return this.isNum(this.twd) ? Number.parseFloat(Number(this.twd) / 0.23).toFixed(3) : ''
      },
      set (val) {
        this.twd = Number.parseFloat(Number(val) * 0.23).toFixed(3)
      }
    },
    usd: {
      get () {
        return this.isNum(this.twd) ? Number.parseFloat(Number(this.twd) / 29.62).toFixed(3) : ''
      },
      set (val) {
        this.twd = Number.parseFloat(Number(val) * 29.62).toFixed(3)
      }
    }
  },
  methods: {
    isNum: function (num) {
      if (num !== '' && !isNaN(num)) {
        return true
      } else {
        return false
      }
    }
  }
}
</script>
