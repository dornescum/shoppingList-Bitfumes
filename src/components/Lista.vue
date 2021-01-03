<template>
  <div class="container text-center grey-color">
    <div class="table-hover table-bordered">
    <h5>{{ title }}<span>:</span> {{ productCount }}</h5>
    <ul class="">
      <li class="flex justify-content-between b-list-group-item"
          v-for="(item,index) in lista" v-bind:key="index">
        <div>{{ item.produs }}</div>
        <button class="btn bg-dark text-white" @click="removeProduct(index)">X</button>
      </li>
    </ul>
    <form  @submit.prevent="addProduct">
      <input class="form-group mt-3 rounded border" v-model="newProduct" placeholder="produs"/>
      <button class="border rounded bg-primary text-white" type="submit">adauga produs</button>
    </form>
    <p>aveti {{productCount}} produse de cumparat</p>
    </div>

  </div>
</template>

<script>
export default {
  computed:{
    productCount(){
      return this.lista.length;
    }
  },
  methods:{
    addProduct(){
      if (this.newProduct !== ''){
        this.lista.push({produs:this.newProduct});
        this.newProduct='';
      }
    },
    removeProduct(index){
      this.lista = this.lista.filter((produs,id) => id!= index)
    }
  },
  name: 'Lista',
  props: {},
  data() {
    return {
      newProduct: '',
      title: 'Lista de cumparaturi',
      isShowing: true,
      count: 0,
      lista: [{produs: 'bere'}, {produs: 'masline'}, {produs: 'varza'}, {produs: 'vin'}, {produs: 'mustar'},
      ],
      // productCount: this.lista.length,
    }
  },
  mounted() {
    setInterval(() => {
      this.count++;
    }, 1000)
  },


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  list-style: none;
}
.flex{
  display: flex;
  padding: 20px 20px;
  margin: 20px 40px;
  border: 1px solid black;
}
.flex:hover{
  background: #ccc;
}
.grey-color {
  background: #f9f9f9;
}
</style>
