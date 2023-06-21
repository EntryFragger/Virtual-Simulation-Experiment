<template>
  <div style="padding-top:60px;padding-bottom:20px">
        <a-config-provider :locale="locale">
            <p style="line-height:200%;font-size: 16px;">
                <a-row justify="center">
                    <a-col span="6">课程名称：软件工程经济学</a-col>
                    <a-col span="6">课号：420279</a-col>
                    <a-col span="6">实验项目名称：软件开发成本估算实验</a-col>
                </a-row>
                <a-row justify="center">
                    <a-col span="6">实验时间：<span style="border-bottom: 1px solid grey;border-radius: none;"><a-date-picker
                                v-model="experimentdate" :bordered="false"
                                style="width:150px;padding-left:3px;padding-right:3px;"
                                placeholder="点击选择实验时间" /></span></a-col>
                    <a-col span="6">实验报告人： <span style="border-bottom: 1px solid grey;border-radius: none;"><a-input
                                v-model="reportername" placeholder="请输入报告人姓名" size="small" :bordered="false"
                                style="width:18vh;"></a-input></span>
                    </a-col>
                    <a-col span="6"></a-col>
                </a-row>
            </p>
        </a-config-provider>
      </div>

  
  
  <div class="GB21_main">
    <h2>一、实验目的  </h2>
    <p class="content">理解软件开发成本估算（GB标准）原理，通过实验操作掌握软件开发成本估算的三种基本方法。本实验为课内设计性实验项目，实验学时 1 学时，完成实验报告 1 学时。
    </p> 
    
    <h2>二、实验原理</h2> 
    <p class="content">
        软件开发过程指从项目立项开始到项目完成验收之间所涉及的需求分析、概要设计、编码实现、集成测试、验收交付及相关的项目管理支持活动。软件开发成本仅包括软件开发过程中的所有人力成本和非人力成本之和,不包括数据迁移和软件维护等成本。人力成本包括直接人力成本和间接人力成本,非人力成本包括直接非人力成本和间接非人力成本。本标准中所涉及工作量也仅为软件开发过程所用工作量。<br>
        &nbsp;&nbsp; &nbsp;&nbsp;直接人力成本包括开发方项目组成员的工资、奖金和福利等人力资源费用。其中,项目成员包括参与该项目开发过程的所有开发或支持人员,如项目经理、需求分析人员、设计人员、开发人员、测试人员、
        部署人员、用户文档编写人员、质量保证人员和配置管理人员等。对于非全职投入该项目开发工作的人员,按照项目工作量所占其总工作量比例折算其人力资源费用。<br>
        &nbsp;&nbsp; &nbsp;&nbsp;间接人力成本指开发方服务于开发管理整体需求的非项目组人员的人力资源费用分摊。包括开发部门经理、项目管理办公室人员、工程过程组人员、产品规划人员、组织级质量保证人员、组织级配置管
        理人员、商务采购人员和IT 支持人员等的工资、奖金和福利等的分摊。<br>
        &nbsp;&nbsp; &nbsp;&nbsp; 直接非人力成本包括: <br>
        &nbsp;&nbsp; &nbsp;&nbsp;a) 办公费,即开发方为开发此项目而产生的行政办公费用,如办公用品、通讯、邮寄、印刷和会 议等;
        <br>
        &nbsp;&nbsp; &nbsp;&nbsp;b) 差旅费,即开发方为开发此项目而产生的差旅费用,如交通、住宿和差旅补贴等; <br>
        &nbsp;&nbsp; &nbsp;&nbsp;c) 培训费,即开发方为开发此项目而安排的培训产生的费用; <br>
        &nbsp;&nbsp; &nbsp;&nbsp;d) 业务费,即开发方为完成此项目开发工作所需辅助活动产生的费用,如招待费、评审费和验收 费等;
        <br>
        &nbsp;&nbsp; &nbsp;&nbsp;e) 采购费,即开发方为开发此项目而需特殊采购专用资产或服务的费用,如专用设备费、专用软
        件费、技术协作费和专利费等;<br>
        &nbsp;&nbsp; &nbsp;&nbsp;f) 其他,即未在以上项目列出但却是开发方为开发此项目所需花费的费用。<br>
        &nbsp;&nbsp; &nbsp;&nbsp;间接非人力成本指开发方不为开发某个特定项目而产生,但服务于整体开发活动的非人力成本分
        摊。包括:开发方开发场地房租、水电和物业,开发人员日常办公费用分摊,战略、市场宣传推广、品牌建
        设、知识产权专利等费用分摊,以及各种开发办公设备的租赁、维修和折旧分摊等。
      </p>

    
    <h2>三、实验步骤 </h2>
    <div class="GB21_card1">
      <span class="GB21_ff1" @click="show1=!show1">方法一
      <span style="font-weight: 400;margin-right: 100px;margin-left: 50px">直接根据定义得出</span>
      </span>
      <div :style="{height:show1?null:'0px'}" style="overflow: hidden;margin-top: 20px">
        <p>直接根据定义得出</p>
        <div class="GB21_grid">
          <div>
            <label>
              直接人力成本=
              <input type="number" v-model="data.method1.directManpowerCost"/>
            </label>
          </div>
          <div>
            <label>
              间接人力成本==
              <input type="number" v-model="data.method1.IndirectLaborCosts"/>
            </label>
          </div>
          <div>
            <label>
              直接非人力成本=
              <input type="number" v-model="data.method1.directNonLaborCosts"/>
            </label>
          </div>
          <div>
            <label>
              间接非人力成本=
              <input type="number" v-model="data.method1.indirectNonLaborCosts"/>
            </label>
          </div>
        </div>
        <div style="display: flex;align-items: center;margin-top: 20px">
          <p>综上: 软件开发成本= </p>
          <span class="GB21_xiahuax">{{ Software_development_costs || '' }}</span>
        </div>
        <p style="text-align: center">SDC = DHC + DNC + IHC + INC</p>
        <ul class="GB21_ui">
          <li>式中:</li>
          <li>SDC---软件开发成本,单位为元</li>
          <li>DHC---直接人力成本,单位为元:</li>
          <li>DN---直接非人力成本,单位为元;</li>
          <li>IH---间接人力成本,单位为元</li>
          <li>IN---间接非人力成本，单位为元</li>
        </ul>
      </div>

    </div>
    <div class="GB21_card2">
      <span class="GB21_ff1" @click="show2=!show2">方法二
       <span
           style="font-weight: 400;margin-right: 100px;margin-left: 50px">先计算人力成本费率，再结合工作量估算结果计算得出</span>
      </span>
      <div :style="{height:show2?null:'0px'}" style="overflow: hidden;margin-top: 20px">
        <p>1.首先跟据直接人力成本费率估算人力成本费率</p>
        <div class="GB21_grid2">
          <div>
            <label>
              间接成本系数=
              <input type="number" v-model="data.method2.indirectCostFactor"/>
            </label>
          </div>
          <div>
            <label>
              直接人力成本费率1=
              <input type="number" v-model="data.method2.directLaborCostRate1"/>
            </label>
          </div>
          <div>
            <label>
              直接人力成本费率2=
              <input type="number" v-model="data.method2.directLaborCostRate2"/>
            </label>
          </div>
          <div>
            <label>
              直接人力成本费率3=
              <input type="number" v-model="data.method2.directLaborCostRate3"/>
            </label>
          </div>
        </div>
        <div>
          <br>
          <br>
          <span>综上:</span>
          <div style="display: flex;align-items: center;margin-top: 15px">
            <span>人力成本费率1= </span>
            <span class="GB21_xiahuax">{{ Labor_cost_rate_1 || '' }}</span>
          </div>
          <div style="display: flex;align-items: center;margin-top: 15px">
            <span>人力成本费率2= </span>
            <span class="GB21_xiahuax">{{ Labor_cost_rate_2 || '' }}</span>
          </div>
          <div style="display: flex;align-items: center;margin-top: 15px">
            <span>人力成本费率3= </span>
            <span class="GB21_xiahuax">{{ Labor_cost_rate_3 || '' }}</span>
          </div>
        </div>
        <p style="text-align: center">F = IF X (1 + DP)</p>
        <ul class="GB21_ui">
          <li>式中:</li>
          <li>F---人力成本费率,单位为元每人月</li>
          <li>IF---直接人力成本费率,单位为元每人月</li>
          <li>DP---间接成本系数，即分摊到每人月的间接成本占每人月直接人力成本的比例</li>
        </ul>
        <p >2.其次依据工作量估算结果和人力成本费率直接计算出直接人力成本和间接成本的总和，然后计算软件开发成本</p>
          <div class="GB21_grid2">
            <div>
              <label>
                直接非人力成本=
                <input type="number" v-model="data.method3.DirectNonLaborCosts"/>
              </label>
            </div>
            <div>
              <label>
                工作量1=
                <input type="number" v-model="data.method3.workload1"/>
              </label>
            </div>
            <div>
              <label>
                工作量2=
                <input type="number" v-model="data.method3.workload2"/>
              </label>
            </div>
            <div>
              <label>
                工作量3=
                <input type="number" v-model="data.method3.workload3"/>
              </label>
            </div>
          </div>
          <br>
          <div style="display: flex;align-items: center;margin-top: 15px">
            <span>综上: 软件开发成本= </span>
            <span class="GB21_xiahuax">{{ Software_development_costs_3 || '' }}</span>
          </div>
          <p style="text-align: center">SDC = (Eᵢ * Fᵢ) + DNC </p>
          <ul class="GB21_ui">
            <li>式中:</li>
            <li>SDC---软件开发成本，单位为元</li>
            <li>n---人员类别数量,取值为不小于的自然数</li>
            <li>Eᵢ---第i类人员的工作量,单位为人月</li>
            <li>Fᵢ---第i类人员的人力成本费率,单位为元每人月</li>
          </ul>
      </div>

    </div>
    <div class="GB21_card3">
      <span class="GB21_ff1" @click="show3=!show3">方法三
           <span
               style="font-weight: 400;margin-right: 100px;margin-left: 50px">根据规模综合单价和估算出的规模计算得出</span>
      </span>
      <div :style="{height:show3?null:'0px'}" style="overflow: hidden;margin-top: 20px">
        <p>根据规模综合单价和估算出的规模直接计算出直接人力成本和间接成本的总和，然后计算软件开发成本</p>
        <div class="GB21_grid2">
          <div>
            <label>
              规模综合单价=
              <input type="number" v-model="data.method4.ComprehensiveUnitPriceOfScale"/>
            </label>
          </div>
          <div>
            <label>
              软件规模=
              <input type="number" v-model="data.method4.SoftwareScale"/>
            </label>
          </div>
          <div>
            <label>
              直接非人力成本=
              <input type="number" v-model="data.method4.DirectNonLaborCosts"/>
            </label>
          </div>
        </div>
        <div style="display: flex;align-items: center;margin-top: 15px">
          <span>综上: 软件开发成本= </span>
          <span class="GB21_xiahuax">{{ Software_development_costs_4 || '' }}</span>
        </div>
        <p style="text-align: center">SDC = P × S + DNC</p>
        <ul class="GB21_ui">
          <li>式中:</li>
          <li>SDC---软件开发成本，单位为元</li>
          <li>p---规模综合单价,单位为元每功能点(元/FP)</li>
          <li>S---软件规模，单位为功能点(FP)</li>
          <li>DNC---直接非人力成本,单位为元</li>
        </ul>
      </div>

    </div>
    <div>
      <h2>四、实验心得</h2>
      <textarea style="margin: 20px auto;display: block" name="" id="" cols="170" rows="20"></textarea>
    </div>
  </div>
  
</template>


<script setup>

import {ref, reactive, computed} from "vue";

let data = reactive({
  method1: {
    directManpowerCost: null,
    IndirectLaborCosts: null,
    directNonLaborCosts: null,
    indirectNonLaborCosts: null
  },
  method2: {
    indirectCostFactor: null,
    directLaborCostRate1: null,
    directLaborCostRate2: null,
    directLaborCostRate3: null
  },
  method3: {
    DirectNonLaborCosts: null,
    workload1: null,
    workload2: null,
    workload3: null
  },
  method4: {
    ComprehensiveUnitPriceOfScale: null,
    SoftwareScale: null,
    DirectNonLaborCosts: null,

  },
})
//方法一
let Software_development_costs = computed(() => {
  console.log(data.method1.directManpowerCost)
  return (data.method1.directManpowerCost || 0) + (data.method1.IndirectLaborCosts || 0) + (data.method1.directNonLaborCosts || 0) + (data.method1.indirectNonLaborCosts || 0)
})
//方法二 第一步 1
let Labor_cost_rate_1 = computed(() => {
  return (data.method2.directLaborCostRate1 || 0 ) * (1 + data.method2.indirectCostFactor || 0)
})
//方法二 第一步 2
let Labor_cost_rate_2 = computed(() => {
  return (data.method2.directLaborCostRate2 || 0 ) * (1 + data.method2.indirectCostFactor || 0)
})
//方法二 第一步 3
let Labor_cost_rate_3 = computed(() => {
  return (data.method2.directLaborCostRate3 || 0 ) * (1 + data.method2.indirectCostFactor || 0)
})
//方法二 第二步
let Software_development_costs_3 = computed(() => {
  return (
      (data.method3.workload1 || 0) * (Labor_cost_rate_1.value || 0) +
      (data.method3.workload2 || 0) * (Labor_cost_rate_2.value || 0) +
      (data.method3.workload3 || 0) * (Labor_cost_rate_3.value || 0) +
      (data.method3.DirectNonLaborCosts || 0)
  )
})
//方法三
let Software_development_costs_4 = computed(() => {
  return (data.method4.ComprehensiveUnitPriceOfScale || 0) * (data.method4.SoftwareScale || 0) + (data.method4.DirectNonLaborCosts || 0)
})


function submit() {

}

let show1 = ref(false)
let show2 = ref(false)
let show3 = ref(false)
</script>
<style scoped>
.GB21submit {
  background-color: rgba(136, 136, 136, 0.66);
  color: black;
  padding: 3px;
  border-radius: 5px;
  border: none;
  float: right;
  margin-bottom: 30px;
}


.GB21_grid2 label input {
  margin-left: 10px;
  border-radius: 5px;
  width: 100px;
}

.GB21_main .GB21_grid2 {
  width: 600px;
  display: grid;
  grid-template-columns: 1fr;
  row-gap: 15px;
  margin-top: 20px;
}

.GB21_main .GB21_ui li {
  list-style: none;
}

.GB21_main .GB21_ui {
  line-height: 1.8;
  margin-left: -35px;
}

.GB21_main .GB21_xiahuax {
  display: inline-block;
  width: 100px;
  height: 20px;
  border-bottom: 1px solid black;
  text-align: center;
}

.GB21_main .GB21_grid label input, .GB21_grid2 label input {
  margin-left: 10px;
  border-radius: 5px;
  width: 100px;
}

.GB21_main .GB21_grid label {
  display: flex;
  display: flex;
}

.GB21_main .GB21_grid {
  width: 600px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  column-gap: 20px;
  row-gap: 20px;
  margin-top: 20px;

}

.GB21_main .GB21_ff1 {
  padding: 3px 8px 3px 8px;
  border-radius: 10px;
  background-color: rgb(161, 154, 151);
  font-weight: bold;
  font-size: 17px;
  text-align: center;
  line-height: 1;
  cursor: pointer;
}

.GB21_main .GB21_card1, .GB21_card2, .GB21_card3 {
  margin-left: 60px;
  margin-top: 40px;
}

.GB21_main {
  width: 1080px;
  margin: 0;
  padding: 0;
}

.GB21_main .GB21_header {
  text-align: center;
  font-size: 20px;
  font-weight: bold;
  height: 50px;
  line-height: 50px;
  background-color: #ccb1ed;
}

.GB21_main .GB21_header p {
  margin: 0;
  padding: 0;
}

.GB21_main .GB21_do {
  display: flex;
  column-gap: 20px;
  margin-top: 20px;
  justify-content: right;
  margin-right: 50px;
}

.GB21_main .GB21_do div {
  background-color: rgba(136, 136, 136, 0.66);
  color: black;
  padding: 3px;
  border-radius: 5px;
}

.GB21_main .GB21_title, .GB21_main .GB21_guoc_title {
  font-size: 20px;
  font-weight: bold;
  margin-top: 20px;
  margin-left: 50px;
}

.content {
    text-indent: 2em;
    margin-left: 20px;
    margin-right: 20px;
}

</style>
