<template>
  <v-app>
    <SideBar />
    <SideBarRight />
    <v-container>
      <v-toolbar color="rgba(0,0,0,0)" flat>
        <v-toolbar-title class="mt-n3">Chọn danh mục sản phẩm</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-text-field
          label="Tìm kiếm danh mục hoặc sản phẩm..."
          class="mt-5"
          color="brown"
          filled
          append-icon="mdi-magnify"
          dense
          solo
          flat
          background-color="grey lighten-4"
        ></v-text-field>
      </v-toolbar>
      <v-item-group mandatory class="mt-n1">
        <v-container>
          <v-row justify="center" class="space">
            <v-col v-for="(item, index) in categories" :key="index" cols="12" md="2">
              <v-item v-slot="{ active, toggle }">
                <category-component
                  :imageURL="item.image"
                  :active="active"
                  :name="item.name"
                  :eventClick="toggle">
                </category-component>
              </v-item>
            </v-col>
          </v-row>
        </v-container>
      </v-item-group>
      <v-toolbar color="rgba(0,0,0,0)" flat>
        <v-toolbar-title class="mt-n3">Menu</v-toolbar-title>
        <v-spacer></v-spacer>
        <span color="grey">12 Results</span>
      </v-toolbar>
      <v-row>
        <v-col v-for="(item, index) in drinks" :key="index" cols="12" sm="6" >
          <drink-item-component
            :name="item.name"
            :imageURL="item.imageURL"
            :description="item.description"
            :unitPrice="item.unitPrice"
          >
          </drink-item-component>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
import SideBar from "../components/SideBar";
import SideBarRight from "../components/SideBarRight";
import CategoryComponent from '../components/category/CategoryComponent.vue';
import DrinkItemComponent from '../components/drink-item/DrinkItemComponent.vue';

export default {
  name: "Home",
  components: {
    SideBar,
    SideBarRight,
    CategoryComponent,
    DrinkItemComponent
  },
  data: () => ({
    categories: [
      {
        name: "Tất cả",
        image: "c1.png"
      },
      {
        name: "Cà phê",
        image: "c2.png"
      },
      {
        name: "Sinh tố / Nước ép",
        image: "c3.png"
      },
      {
        name: "Đá xay",
        image: "c4.png"
      },
      {
        name: "Bánh ngọt",
        image: "c5.png"
      },
    ],
    drinks: [
      {
        name: "Caramel Frappuccino",
        imageURL: "2.png",
        unitPrice: 100,
        description: "Caramel sytrup with coffee, milk, and whipped cream"
      }
    ]
  })
};
</script>
