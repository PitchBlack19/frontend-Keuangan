<script>


export default{
  data(){
    return{
      datasensor :"Belum ada"
    }
  },

  created(){
    this.sambutan()
  },
  
  methods:{
    sambutan(){
      alert("selamat datang");
    },
    async updata(){
      const data = await fetch("http://127.0.0.1:82/getdata")
      const datanya1 = await data.json()
      this.datasensor = datanya1.postData
    }
  }
}
//tempat ngoding javascript
</script>

<template>
<!----tempat ngoding html-->
  <div>
    Laporan keuangan {{ datasensor }}
    <button @click="updata">dapatkan</button>
  </div>
  
</template>