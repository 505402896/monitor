<template>
  <div class="app">
    <header>
      <h1>山东经典重工大数据云图</h1>
      <!-- <a href="#">山东经典重工大数据云图</a> -->
    </header>
    <main>
      <div class="left">
        <div class="project-list project">
          <div class="title">项目列表</div>
          <table>
            <thead>
              <th>项目名称</th>
              <th>完成占比</th>
            </thead>
            <tbody></tbody>
          </table>
        </div>
        <div class="project-analyse project">
          <div class="title">项目月安装分析</div>
          <div class="pic"></div>
        </div>
        <div class="attendance project">
          <div class="title">工地今日出勤</div>
          <table>
            <thead>
              <th>工种</th>
              <th>人员</th>
              <th>出勤</th>
              <th>缺勤</th>
            </thead>
            <tbody></tbody>
          </table>
        </div>
      </div>
      <div class="center">
        <div class="title">
          <h2>***国际办公c区</h2>
        </div>
        <div class="data">
          <div class="data__left">
            <div class="data__left-up">
              <div>
                <div class="icon"></div>
                <h3>XXX</h3>
                <p>今日施工人数</p>
              </div>
              <div>
                <div class="icon"></div>
                <h3>XXX</h3>
                <p>今日施工人数</p>
              </div>
              <div>
                <div class="icon"></div>
                <h3>XXX</h3>
                <p>今日施工人数</p>
              </div>
            </div>
            <div class="data__left-down">
              <div>
                <div class="icon"></div>
                <h3>XXX</h3>
                <p>今日施工人数</p>
              </div>
              <div>
                <div class="icon"></div>
                <h3>XXX</h3>
                <p>今日施工人数</p>
              </div>
              <div>
                <div class="icon"></div>
                <h3>XXX</h3>
                <p>今日施工人数</p>
              </div>
            </div>
          </div>
          <div class="data__right">
            <div>
              <span>PM2.5:</span><b>33μg/m3</b>
            </div>
            <div>
              <span>PM10:</span><b>33μg/m3</b>
            </div>
            <div>
              <span>SO2:</span><b>33μg/m3</b>
            </div>
            <div>
              <span>NO2:</span><b>33μg/m3</b>
            </div>
            <div>
              <span>O3:</span><b>33μg/m3</b>
            </div>
            <div>
              <span>CO:</span><b>33μg/m3</b>
            </div>
          </div>
        </div>
        <!-- 改为iframe -->
        <div class="model">
          <div class="model__title">
            <i style="background:rgb(153,153,153)"></i><span>无清单</span>
            <i style="background:rgb(255,255,255)"></i><span>未生产</span>
            <i style="background:rgb(255,186,0)"></i><span>生产中</span>
            <i style="background:rgb(22,130,230)"></i><span>生产完毕</span>
            <i style="background:rgb(50,211,166)"></i><span>安装完毕</span>
          </div>
        </div>
      </div>
      <div class="right">
        <div class="monitor"></div>
        <div class="monitor"></div>
        <div class="monitor"></div>
      </div>
    </main>
  </div>
</template>

<script>
import echarts from 'echarts'
export default {
  name: 'App',
  data () {
    return {
      myChart: null
    }
  },
  mounted () {
    this.$nextTick(() => {
      this.init()
    })
  },
  methods: {
    init () {
      this.myChart = echarts.init(document.querySelector('.pic'))
      this.myChart.setOption({
        grid: {
          top: '30px',
          left: '30px',
          right: '10px',
          bottom: '30px'
        },
        label: {
          show: true
        },
        textStyle: {
          color: '#d6e0eb'
        },
        xAxis: {
          type: 'category',
          data: ['1月', '2月', '3月', '4月', '5月', '6月', '7月', '8月', '9月', '10月', '11月', '12月']
        },
        yAxis: {
          axisTick: {
            show: false
          },
          type: 'value',
          data: [0, 420, 840, 1260, 1680, 2100]
        },
        color: ['#0a73ff'],
        series: [{
          data: [0, 0, 0, 0, 0, 926, 1849, 1852, 1862, 1856, 1851, 1752],
          type: 'bar',
          barWidth: 15,
          showBackground: true,
          backgroundStyle: {
          }
        }]
      })
    }
  }
}
</script>

<style lang="scss">

$--primary-blue: #5fd0f1;
$--light-blue: #6bc1ff;
$--bc-blue: rgba(52, 136, 237, 0.5);
$--grey: rgb(214,224,235);

  *{
    padding: 0;
    margin: 0;
  }
  body{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    background: url('./img/2.jpg');
  }
  .app{
    position: relative;
    width: 100%;
    height: 100%;
  }
  header{
    width: 100%;
    height: 150px;
    margin-top: -50px;
    background: url('./img/3.png');
    h1{
      width: 100%;
      color: $--primary-blue;
      text-align: center;
      line-height: 200px;
    }
    a{
      display: block;
      color: unset;
      text-decoration: none;
      background-image: linear-gradient(0deg, rgb(3, 175, 239) 0%, rgb(189, 240, 241) 95%);
      -webkit-text-fill-color: transparent;
      overflow: unset;
      white-space: unset;
      text-overflow: unset;
    }
  }
  main{
    display: flex;
    margin: 0 30px;
    // width: 100%;
    height: calc( 100vh - 150px );
  }
  .center{
    width: 900px;
    height: 100%;
    margin: 0 20px;
    .title{
      height: 56px;
      background: $--light-blue;
      border-radius: 10px;
      h2{
        color: #fff;
        line-height: 56px;
        font-size: 24px;
        text-align: center;
        font-weight: normal;
      }
    }
    .data{
      position: relative;
      height: 184px;
      margin-bottom: 15px;
      color: #fff;
      .icon{
        float: left;
        width: 50px;
        height: 50px;
        margin: 0 10px;
        background: wheat;
      }
      &__left{
        position: relative;
        float: left;
        margin: 20px 0;
        width: 80%;
        height: 100%;
        &-up{
          display: flex;
          width: 100%;
          height: 50%;
          div{
            flex: 1;
          }
        }
        &-down{
          display: flex;
          width: 100%;
          height: 50%;
          div{
            flex: 1;
          }
        }
      }
      &__right{
        float: left;
        width: 20%;
        height: 100%;
        font-size: 17px;
        margin: 20px 0;
        line-height: 25px;
        span{
          color: $--light-blue;
        }
        b{
          margin-left: 10px;
        }
      }
    }
    .model{
      position: relative;
      height: 495px;
      background-color: $--grey;
      border-image: url('./img/1.png') 32 37 fill / 32px 37px / 0 stretch;
      &__title{
        position: absolute;
        top: 20px;
        left: 20px;
        z-index: 9;
        height: 30px;
        i{
          display: inline-block;
          width: 20px;
          height: 20px;
          border-radius: 50%;
          background: #fff;
          vertical-align: middle;
        }
        span{
          display: inline-block;
          font-size: 14px;
          margin: 0 10px;
          line-height: 20px;
        }
      }
    }
  }
  .left{
    flex: 1;
    height: 100%;
    .project{
      height: 240px;
      margin-bottom: 15px;
      border-image: url('./img/1.png') 32 37 fill / 32px 37px / 0 stretch;
      .title{
        height: 20px;
        line-height: 20px;
        color: #fff;
        margin-left: 10px;
      }
      .pic{
        width: 100%;
        height: calc( 100% - 20px );
      }
      table{
        width: 100%;
        color: #fff;
        font-size: 10px;
        thead{
          background: $--bc-blue;
        }
      }
    }
  }
  .right{
    flex: 1;
    height: 100%;
    .monitor{
      height: 240px;
      margin-bottom: 15px;
      border-image: url('./img/1.png') 32 37 fill / 32px 37px / 0 stretch;
    }
  }
</style>
