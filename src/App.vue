<script setup>
import IconButton from './components/IconButton.vue'
import Input from './components/Input.vue'
import { ref } from 'vue'

const items = [
  {
    content: 'Microsoft',
    icon: 'icon',
    subMenu: [
      {
        content: 'Windows',
        icon: 'icon'
      },
      {
        content: 'Office',
        icon: 'icon'
      },
      {
        content: 'Surface',
        icon: 'icon'
      }
    ]
  },
  {
    content: 'Apple',
    icon: 'icon',
    subMenu: [
      {
        content: 'iPhone',
        icon: 'icon'
      },
      {
        content: 'Mac',
        icon: 'icon'
      },
      {
        content: 'iPad',
        icon: 'icon'
      },
      {
        content: 'Watch',
        icon: 'icon'
      },
      {
        content: 'Music',
        icon: 'icon'
      }
    ]
  }
]
const list = [
  {
    headline: 'headline',
    supportingText: 'supportingText',
    href: 'https://www.baidu.com',
    target: '_blank',
    startImage: 'https://www.baidu.com/img/flexible/logo/pc/result.png',
    endImage: 'https://www.baidu.com/img/flexible/logo/pc/result.png'
  },
  {
    headline: 'headline',
    supportingText: 'supportingText',
    href: 'https://www.baidu.com',
    target: '_blank'
  },
  {
    headline: 'headline',
    supportingText: 'supportingText',
    href: 'https://www.baidu.com',
    target: '_blank'
  },
  {
    headline: 'headline',
    supportingText: 'supportingText',
    href: 'https://www.baidu.com',
    target: '_blank'
  },
  {
    headline: 'headline',
    supportingText: 'supportingText',
    href: 'https://www.baidu.com',
    target: '_blank'
  },
  {
    headline: 'headline',
    supportingText: 'supportingText',
    href: 'https://www.baidu.com',
    target: '_blank'
  },
  {
    headline: 'headline',
    supportingText: 'supportingText',
    href: 'https://www.baidu.com',
    target: '_blank'
  },
  {
    headline: 'headline',
    supportingText: 'supportingText',
    href: 'https://www.baidu.com',
    target: '_blank'
  }
]
const menu = ref(null)
const open = () => {
  menu.value.open()
}
const handleSubmit = (content) => {
  console.log(content)
}
const handle = () => {
  console.log(input.value.checkValidity)
}
const input = ref(null)
</script>

<template>
  <!-- <Select :items="items" type="outline"></Select> -->
  <!-- <span style="position: absolute">
    <Button type="filled" label="打开菜单" id="button" @click="open"></Button>

    <Menu
      anchor="button"
      ref="menu"
      :items="items"
      @submit="handleSubmit"
      anchorCorner="end-end"
      menuCorner="start-start"
    ></Menu>
  </span> -->
  <IconButton @click="handle"></IconButton>
  <Input
    type="filled"
    label="password"
    :error="true"
    errorText="密码错误"
    format="number"
  >
    <IconButton slot="trailing-icon" type="ordinary" :toggle="true">
      <svg
        t="1704860491056"
        class="icon"
        viewBox="0 0 1024 1024"
        version="1.1"
        xmlns="http://www.w3.org/2000/svg"
        p-id="2422"
      >
        <path
          d="M512 192C298.666667 192 116.48 324.693333 42.666667 512c73.813333 187.306667 256 320 469.333333 320 213.546667 0 395.52-132.693333 469.333333-320-73.813333-187.306667-255.786667-320-469.333333-320z m0 533.333333c-117.76 0-213.333333-95.573333-213.333333-213.333333s95.573333-213.333333 213.333333-213.333333 213.333333 95.573333 213.333333 213.333333-95.573333 213.333333-213.333333 213.333333z m0-341.333333c-70.613333 0-128 57.386667-128 128s57.386667 128 128 128 128-57.386667 128-128-57.386667-128-128-128z"
          fill=""
          p-id="2423"
        ></path>
      </svg>
      <template #selected>
        <svg
          t="1704860506860"
          class="icon"
          viewBox="0 0 1024 1024"
          version="1.1"
          xmlns="http://www.w3.org/2000/svg"
          p-id="2576"
        >
          <path
            d="M512 298.666667c117.76 0 213.333333 95.573333 213.333333 213.333333 0 27.52-5.546667 53.76-15.146666 77.866667l124.8 124.8c64.426667-53.76 115.2-123.306667 146.56-202.666667-74.026667-187.306667-256-320-469.546667-320-59.733333 0-116.906667 10.666667-170.026667 29.866667l92.16 91.946666c24.106667-9.386667 50.346667-15.146667 77.866667-15.146666zM85.333333 182.4l97.28 97.28 19.413334 19.413333C131.626667 354.133333 75.946667 427.306667 42.666667 512c73.813333 187.306667 256 320 469.333333 320 66.133333 0 129.28-12.8 187.093333-36.053333l18.133334 18.133333L841.6 938.666667 896 884.48 139.733333 128 85.333333 182.4zM321.28 418.133333l65.92 65.92c-1.92 9.173333-3.2 18.346667-3.2 27.946667 0 70.613333 57.386667 128 128 128 9.6 0 18.773333-1.28 27.733333-3.2l65.92 65.92C577.28 716.8 545.706667 725.333333 512 725.333333c-117.76 0-213.333333-95.573333-213.333333-213.333333 0-33.706667 8.533333-65.28 22.613333-93.866667z m183.68-33.493333l134.4 134.4L640 512c0-70.613333-57.386667-128-128-128l-7.04 0.64z"
            p-id="2577"
          ></path>
        </svg>
      </template>
    </IconButton>
  </Input>

  <Input
    ref="input"
    type="filled"
    label="dollar count"
    prefixText="$"
    suffixText=".00"
    format="number"
    value="0"
    supportingText="please input your dollar count"
  >
  </Input>
  <Input format="textarea"></Input>
  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
