<template>
  <div class="vps-main-content" id="testpadding">
      <vps-drawer>
      </vps-drawer>
    <div class="vps-main">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import { List, ListItem } from "../components/lists";
import Card from "../components/containers/Card";
import Icon from "../components/icons";
import Drawer from "../components/containers/Drawer";
import Button from "../components/actions/Button";

export default {
  data() {
    return {
      showThemeSettings: false,
      themeCol: ""
    };
  },
  computed: {
    drawerClasses() {
      return {
        "vps-theme-settings-hidden": !this.showThemeSettings,
        "vps-theme-settings-shown": this.showThemeSettings
      };
    }
  },
  methods: {
    chooseTheme(color, newTheme = true) {
      document.documentElement.style.setProperty(
          "--side-bg-color",
          color.sidebarColor
      );
      document.documentElement.style.setProperty(
          "--header-bg-color",
          color.headerColor
      );
      document.documentElement.style.setProperty(
          "--sidebarColor",
          color.sidebarColor
      );
      document.documentElement.style.setProperty(
          "--headerColor",
          color.headerColor
      );
      if (newTheme) {
        localStorage.setItem("vpscolor", JSON.stringify(color));
      }
    }
  },
  components: {
    List,
    ListItem,
    Card,
    Icon,
    "vps-drawer": Drawer,
    "vps-button": Button
  },
  mounted() {
    let defaultTheme = {
      sidebarColor: "#0FA774",
      headerColor: "#a7a409"
    };
    try {
      let item = localStorage.getItem("vpscolor");

      let theme = item ? JSON.parse(item) : defaultTheme;
      this.chooseTheme(theme, false);
    } catch (error) {
      this.chooseTheme(defaultTheme, false);
    }
  }
};
</script>

<style>
#testpadding {
  padding: 0;
}

.vps-theme-settings {
  display: flex;
  align-items: center;
  position: absolute;
}
.vps-theme-settings-hidden {
  right: -280px;
  transition: all 1s;
}
.vps-theme-settings-shown {
  right: 0;
  transition: all 1s;
}
.vps-theme-colors {
  padding: 10px;

  display: grid;
  grid-template-columns: 100%;
  grid-gap: 8px;
}

.vps-theme-colors h4 {
  text-align: center;
  color: #555;
}

.vps-theme-colors .vps-theme-color {
  display: flex;
  cursor: pointer;
}

.vps-theme-colors .vps-theme-color .color {
  height: 24px;
  width: 200px;
}
</style>
