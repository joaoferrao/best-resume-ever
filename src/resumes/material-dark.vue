<template>
<div class="resume">
  <div class="leftCol m_box">
    <div class="shadow"></div>
    <div class="heading" id="myselfpic">
    </div>
    <div class="section-headline">
      {{ lang.contact }}
    </div>
    <div class="item" v-for="contact in person.contact" :key="contact.type">
        <div class="text">
            <span class="empty-space">&nbsp;</span><span>{{ contact.type }}</span>
        </div>
    </div>
    <div class="item last">
      <div class="section-headline">{{ lang.skills }}</div>
      <div class="skill">
        <div class="left">
          <span v-for="skill in person.skills" :key="skill.name">
            <span>{{skill.name}}</span>
          </span>
        </div>
      </div>
    </div>
    <div class="item">
      <div class="section-headline">Recommendations</div>
      <div class="rec-box">
        <div class="recommendation"> {{person.recommendation.rec}}</div>  
        <div class="recommender"> {{person.recommendation.name}}</div>  
        <div class="position"> {{person.recommendation.title}}</div>  
      </div>
    </div>
  </div>
  <div class="rightCol">
    <div class="title">
      <h2>{{person.name.first}} {{person.name.middle}} {{person.name.last}}</h2>
      <div>{{person.position}}</div>
    </div>
    <div class="section-headline">{{ lang.about }}</div>
      <div class="block">
        <div class="about" v-for="about in person.about" :key="about.par">
            <span> {{about.par}}</span>
        </div>
      </div>
    <div class="section-headline">{{ lang.experience }}</div>
    <div class="block" v-for="experience in person.experience" :key="experience.company">
      <div class="headline">
        <span> {{experience.position}} - {{experience.company}}</span>
        <span class="subheadline">{{experience.timeperiod}}</span>
      </div>     
        <p class="info" v-html="experience.description">
          <!-- {{experience.description}} -->
        </p>
    </div>
    <div class="section-headline">{{ lang.education }}</div>
    <div class="block" v-for="education in person.education" :key="education.degree">
      <div class="headline">{{education.degree}}</div>
      <p class="info">
        {{education.timeperiod}}, {{education.description}}
      </p>
    </div>
  </div>

  <div style="clear:both;"></div>
</div>
</template>

<script>
import Vue from 'vue';
import { getVueOptions } from './options';
let name = 'material-dark';

export default Vue.component(name, getVueOptions(name));
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
.resume {
  font-family:'Arial' !important;
  font-family: 'Roboto', sans-serif;
  font-weight: 300;
  // background-color:#f3f3f3;
  background-color:white;
  color: #767676;
  font-size: 14px;
}
a {
  cursor:pointer;
}
.description-personal {
  margin-left:20px;
  margin-top:20px;
  padding-right:40px;
  text-align:justify;
  font-family:Roboto;
}
.title {
  right:25px;
  // padding-left:20px;
  padding-top:20px;
  // bottom:25px;
  h2 {
    text-transform:uppercase;
    display:block;
    // font-size:1.17em;
    // -webkit-margin-before:1em;
    // -webkit-margin-after:1em;
    -webkit-margin-start:0;
    -webkit-margin-end:0;
    color:#5164a0;
    padding-top:0;
    margin-top:0;
    // letter-spacing:10px;
    font-weight:400;
  }
  div {
    margin-top:-5px;
    margin-top:0;
    margin:0;
    padding:0;
    line-height:15pt;
    font-weight:300;
    font-weight:500;
    // letter-spacing:2px;
    // letter-spacing:3px;
    // color:white;
    // color:#16151c;
    // color:rgba(63,61,60,0.71);
    display:block;
    // font-size:0.67em;
    // font-size:10pt;
    -webkit-margin-before:0;
    -webkit-margin-start:0;
    -webkit-margin-end:0;
    padding-top:0;
    text-transform:uppercase;
    opacity:0.8;
  }
}
.section-headline {
  width:97%;
  // padding-right:px;
  margin-right:5px;
  font-family:'Roboto';
  text-transform:uppercase;
  font-weight:600;
  border-bottom:1px solid #ccc;

  // letter-spacing:3px;
  font-size:13px;
  margin-bottom:3px;
  // opacity:0.8;
  // margin-left:5px;
  margin-top:20px;
  // margin-bottom:20px;
  color:#5164a0;
}
.c {
  clear:both;
}
li {
  margin:0;
  padding:0;
  list-style-type:none;
  padding-top:9px;
}
ul {
  margin:0;
  padding:0;
  list-style-type:none;
}
p {
  font-family:'Roboto', sans-serif;
  font-weight:300;
}
.m_box {
  border-right: 1px solid #ccc;
}
.fa, .material-icons {
  font-family: 'Material Icons';
  display:inline-block;
  font-style:normal;
  font-weight:normal;
  line-height:1;
  -webkit-font-smoothing:antialiased;
  -moz-osx-font-smoothing:grayscale;
  font-size:26px;
}
h1, h3, h5, h6 {
  font-weight:400;
  margin:0;
}
h2 {
  font-weight:400;
  font-weight:500;
  margin:0;
  margin:0;
}
h4 {
  font-weight:400;
  margin:0;
  line-height:20pt;
  opacity:1;
}
.rightCol {
  width:68%;
  height:100%;
  float:right;
  flex-direction:column;
  .about {
    font-weight: 300;
  }
  .block {
    width:95%;
    position:relative;
    padding-right:5px;
    padding-top: 10px;
    padding-bottom: 10px;
    .about{
      font-family: 'Roboto', sans-serif;
      font-weight: 300;
      margin-bottom: 5px;
    }
    .headline {
      font-weight:300;
      display:inline-block;
    }
    .subheadline {
      display:inline-block;
      font-size:12px;
      font-weight:300;
    }
    .info {
      margin-bottom:0;
      margin-top: 5px;
      line-height: 1.3;
      // color: red;
    }
    .icon {
      width:16%;
      float:left;
      margin-left:0;
      .fa, .material-icons {
        text-align:center;
        display:block;
      }
    }
    .content {
      width:80%;
      position:absolute;
      height:96%;
      left:17%;
      padding-right:3%;
      text-align:left;
      display:flex;
      flex-direction:column;
      .item {
        border-bottom:1px solid #bdbdbd;
        flex:1;
        width:97%;
        display:flex;
        justify-content:center;
        flex-direction:column;
        text-align:left;
        padding-top:0;
        span {
          color:#d8ab94;
          margin-top:0;
          line-height:16pt;
        }
        p {
          margin-top:-10px;
        }
      }
      .item:last-of-type {
        border-bottom-style:none;
        border-bottom-style:none;
      }
    }
  }
}
.leftCol {
  width:30%;
  height:100%;
  float:left;
  padding:0;
  text-align:left;
  background-color:#f5f5f5;
  overflow:hidden;
  display:block;
  .section-headline {
    border-bottom:1px solid #ccc;
    width: 90%;
    margin-left: 10px;
    padding-right: 5px;
  }
  .span-icon {
    color:red;
    background-color: black;
    padding-bottom: 10px;
  }
  a {
    text-decoration:none;
  }
  .heading {
    background-color:white;
    background-repeat:no-repeat;
    background-size:cover;
    background-position:center;
    position:relative;
    width:100%;
    height:277px;
  }
  .contact-block {
    display: block;
    color: red;
    background-color: blue;
    span {
      color: black;
      display:inline-block;
      margin-bottom: 10px;
      margin-top: 10px;
      // vertical-align: top;
    }
  }
  .item {
    width:100%;
    margin-top:13px;
    float:left;
    .fa, .material-icons {
      display: inherit;
      text-align: center;
    }
    .text {
      font-family:'Roboto', sans-serif;
      font-weight: 300;
      width:69%;
      padding-right:10%;

      margin-left: 10px;
      display:block;
      font-weight:300;
      .empty-space{
        background-color: rgb(225, 225, 225);
        margin-right: 10px;
      }
      span{
        display: inline-block;
        vertical-align: middle;
      }
      li {
        padding-top:0;
        display:block;
        font-weight:300;
      }
    }
    span {
      font-weight:300;
    }
    .skill {
      clear:both;
      // display:flex;
      width:97%;
      padding-top:8px;
      padding-left: 10px;
      div.left {
        span{
          display:inline-block;
          background-color: rgb(225, 225, 225);
          padding: 2px 2px 2px 2px;
          margin: 2px 2px 2px 2px;
        }
      }
    }
  }
  .item.last .text {
    border-bottom-style:none;
    padding-bottom:0;
  }
  .rec-box {
    margin-top:5px;
    margin-left: 12px;
    margin-right: 10px;
    font-family: 'Roboto', sans-serif;
    font-weight: 300;
    .recommendation {
      font-style: italic;
      line-height: 150%;
    }
    .recommender {
      margin-top:10px;
      font-style: bold;
    }
    .position {
      margin-top:5px;
      font-style: bold;
      font-size: 11px;
      text-transform: uppercase;
    }
  }
}
#myselfpic {
  background-image:url('../../resume/id.jpg');
  color:black;
}
#githubIcon {
  width:25px;
  padding-left:17px;
}
</style>
