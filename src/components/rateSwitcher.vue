<script setup lang="ts">
</script>
<template>
  <RouterLink to="/">返回
  </RouterLink>
  <div class="overview_info col-12 col-md-12 desktop">
    <div class="III-block-white fc">
      <h5 class="fc-title">
        <span>外匯換算</span>
        <i class="fas fa-sort-down"></i>
      </h5>
      <div class="fc-slide">
        <div class="fc-hint">
          <p><span> <i class='fas fa-exclamation-triangle'></i>
              外幣兌台幣資料表，實際資料以各銀行兌換利率為準。
            </span></p>
          <span>(來源：<a href="https://www.taifex.com.tw/cht/index" target="_blank">期交所</a>)</span>
        </div>
        <div class="fc-switcher">
          <div class="fc-currency">
            <input id="inputTwdDesktop" class="form-md" min="0" type="number" value="1">
            <div class="border-left"></div>
            <div class="fc-twd">新臺幣</div>
          </div>
          <div class="fc-currency">
            <input id="inputForeDesktop" class="form-md" min="0" type="number">
            <div class="border-left"></div>
            <select class="form-md" name="curDesktop" id="curDesktop">
              <option value="USD">美元</option>
              <option value="AUD">澳幣</option>
              <option value="CNY">人民幣</option>
            </select>
          </div>
        </div>
        <div class="chartWrap">
          <div class="legendGroup">
            <button value="7" class="legend legend--init legend--active">7天</button>
            <button value="30" class="legend">1個月</button>
            <button value="90" class="legend">3個月</button>
            <button value="180" class="legend">6個月</button>
            <button value="365" class="legend">1年</button>
            <button value="2006-01-01" class="legend">最久</button>
          </div>
          <div id="lineChart" class="line-chart"></div>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.fc {
  flex-direction: column;
}

.fc-title {
  display: flex;
  width: 100%;
  justify-content: space-between;
  cursor: pointer;
}

.fc-title i {
  margin: 0;
}

.fc-slide {
  // display: none;
  margin-top: 24px;
}

.fc-switcher {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 0 8px;
}

.desktop .fc-switcher {
  flex-direction: row;
  justify-content: space-between;
}

.desktop .fc-currency {
  width: calc(50% - 8px);
}

.fc-currency {
  flex-direction: row;
  display: flex;
  width: 100%;
  justify-content: space-between;
  align-items: center;
  border-radius: 6px;
  border: 1px solid #D9D9D9;
  margin-bottom: 12px;
}

.fc-currency select,
.fc-currency input {
  border: none;
  margin-top: 0 !important;
}

.fc-currency .border-left {
  height: 1.5em;
}

.fc-currency select,
.fc-twd {
  font-size: 16px;
  flex: 0 0 40%;
  max-width: 40%;
  padding: 0 8px;
}

.fc-currency svg {
  transform: rotateZ(90deg);
}

.fc-hint {
  margin-bottom: 24px;
  font-size: 12px;
  display: flex;
  flex-direction: column;

  @media screen and (min-width: 500px) {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    font-size: 14px;
  }
}

.fc-hint p {
  color: #ff6a82;
  display: flex;
  width: fit-content;
  text-align: left;
  align-items: center;
}

.fc-hint i {
  font-size: 12px;

  @media screen and (min-width: 500px) {
    font-size: 14px;
  }
}

.fc-source {
  text-align: right;
  font-size: 12px;

  @media screen and (min-width: 500px) {
    font-size: 14px;
  }
}

.fc-hint a {
  text-decoration: underline;
}

.chartWrap {
  width: 100%;
  overflow: auto;
}

.chartWrap::-webkit-scrollbar {
  height: 8px;
}

.chartWrap::-webkit-scrollbar-track {
  background: #f1f1f1;
  border-radius: 4px
}

.chartWrap::-webkit-scrollbar-thumb {
  background: #CFD6E3;
  border-radius: 4px;
}

.chartWrap::-webkit-scrollbar-thumb:hover {
  background: #4f6b99
}

.line-chart {
  width: 100vw;
  min-width: 500px;
  height: 35vh;


  @media screen and (min-width:992px) {
    height: 50vh;
    width: 902px;
  }

  @media screen and (min-width:1201px) {
    width: 1092px;
  }
}

.legendGroup {
  margin-top: 24px;
  display: flex;
  justify-content: space-around;
  width: 100%;

  @media screen and (min-width:991px) {
    justify-content: flex-start;
    padding-left: 50px;

  }
}

.legend {
  padding: 8px 10px;
  border-radius: 6px;
  background: transparent;

  @media screen and (min-width:500px) {
    width: 62px;
    padding: 8px 16x;
  }

  @media screen and (min-width:991px) {
    width: 85px;
    padding: 8px 20px;
    margin-right: 20px;
  }
}

.legend:hover,
.legend--active {
  background-color: #1e2b58;
  color: #fff;
} 
</style>