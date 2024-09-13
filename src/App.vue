<script setup>
import { ToastComponent as EjsToast } from 
'@syncfusion/ej2-vue-notifications';
import { ButtonComponent as EjsButton } from 
'@syncfusion/ej2-vue-buttons';
import { ref } from 'vue';
const position = { X: 'Right', Y: 'Top' };
const toastObj = ref(null);
const showToast = () => {
  toastObj.value.show();
};
const hideToast = () => {
  toastObj.value.hide('All');
};
</script>

<template>
<div class="container">
  <ejs-button v-on:click="showToast">Show Toast</ejs-button>
  <ejs-button v-on:click="hideToast">Hide All</ejs-button>
  <ejs-toast ref="toastObj" :template="'toasttemplate'"
  :position="position" timeOut="0">
  <template v-slot:toasttemplate>
    <div>
      <div className="horizontal-align">
        <div className='toast-content'>
          <div className='toast-title'>
            Weekend Alarm
          </div>
          <div className='toast-message'>
            With traffic, its likely to take 45 minutes to get to jenny's 
            24th Birthday Bash at Hillside Bar, 454 E.Olive Way by 10:00PM
          </div>
        </div>
      </div>
      <img src='https://ej2.syncfusion.com/demos/src/toast/resource/map.jpg' />
    </div>
  </template>
  </ejs-toast>
</div>
</template>

<style>
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-notifications/styles/material.css";
@import '../node_modules/@syncfusion/ej2-buttons/styles/material.css';
.container {
 padding-bottom: 400px;
}
.e-btn {
  margin: 10px
}
img {
  padding-bottom: 20px !important;
  width: 100%;
  height: 66%;
}
.toast-content {
  display: inline-flex;
  flex: 1;
  flex-direction: column;
  padding-bottom: 5px;
}
.toast-title {
  font-weight: bold; 
  padding-bottom: 5px;
  color: #fff;
}
.toast-message {
  padding-bottom: 5px;
}
</style>
