<template>
  <a-layout id="components-layout-demo-custom-trigger">
    <a-layout-sider
      :trigger="null"
      collapsible
      v-model="collapsed"
    >
      <div class="logo" />
      <a-menu theme="dark" mode="inline" :defaultSelectedKeys="['1']">
        <a-menu-item key="1">
          <a-icon type="user" />
          <span>nav 1</span>
        </a-menu-item>
        <a-menu-item key="2">
          <a-icon type="video-camera" />
          <span>nav 2</span>
        </a-menu-item>
        <a-menu-item key="3">
          <a-icon type="upload" />
          <span>nav 3</span>
        </a-menu-item>
      </a-menu>
    </a-layout-sider>
    <a-layout>
      <a-layout-header style="background: #fff; padding: 0">
        <a-icon
          class="trigger"
          :type="collapsed ? 'menu-unfold' : 'menu-fold'"
          @click="()=> collapsed = !collapsed"
        />
      </a-layout-header>
      <h1 :style="{ margin: '16px 16px'}">Company Profile</h1>
      <a-layout-content :style="{ margin: '0 16px 16px 16px', padding: '0 24px', background: '#fff', minHeight: '280px' }">
        <BaseGenSet
          alertmsg="This effort below should not take like two days. Assuming you are only making this. Because I did it like 2 hours from scratch."
          smallTitle="General Information"
          :detailInfo="[
            { title: 'Company ID', text: '001' },
            { title: 'Company Name', text: 'CiakCiak.com' },
            { title: 'Company NPWP Number', text: '00112233445566' },
            { title: 'Billing Address', text: 'Jl. Besar, Lebaran, Kota, Negara 12345' },
            { title: 'Terms of Payment', text: '14 days' },
            { title: 'Credit Limit', text: 'Rp50,000,000' },
            { title: 'Outstanding Balance', text: 'Rp7,000,000' },
            { title: 'CiakCiak Points', text: '345,090 pts' }
          ]"
        />
      </a-layout-content>
      <a-layout-content :style="{ margin: '0 16px 16px 16px', padding: '0 24px', background: '#fff', minHeight: '280px' }">
        <BaseGenSet
          smallTitle="Person in Charge"
          :detailInfo="[
            { title: 'Name', text: 'Srikandi Arjuna Bersatu ' },
            { title: 'Email', text: 'srimriwing@gmail.com' },
            { title: 'Mobile Number', text: '081234567890' }
          ]"
        />
      </a-layout-content>
    </a-layout>
  </a-layout>
</template>

<script>
import BaseGenSet from './components/BaseGenSet.vue';
export default {
  name: 'app',
  data(){
    return {
      collapsed: false,
    }
  },
  components: {
    BaseGenSet
  }
}
</script>
<style>
#components-layout-demo-custom-trigger {
  height: 100vh;
}

#components-layout-demo-custom-trigger .trigger {
  font-size: 18px;
  line-height: 64px;
  padding: 0 24px;
  cursor: pointer;
  transition: color .3s;
}

#components-layout-demo-custom-trigger .trigger:hover {
  color: #1890ff;
}

#components-layout-demo-custom-trigger .logo {
  height: 32px;
  background: rgba(255,255,255,.2);
  margin: 16px;
}
</style>
