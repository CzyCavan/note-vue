<template>
  <div id="app" >



      <el-row style="margin-bottom: 1%">



<!--          侧边导航-->
        <el-col :span="1" >


            <el-menu  :default-active="navIndex"  :collapse="true">





                <el-menu-item index="write" @click="Link('write')">
                    <i class="el-icon-edit"></i>
                    <span slot="title" >Write</span>
                </el-menu-item>




                <el-menu-item index="files" @click="Link('files')">
                    <i class="el-icon-folder-opened"></i>
                    <span slot="title">Folder</span>
                </el-menu-item>








                <el-menu-item index="rubbish" @click="Link('rubbish')">
                    <i class="el-icon-delete"></i>
                    <span slot="title">Rubbish</span>
                </el-menu-item>



                <el-menu-item index="mybook" @click="Link('mybook')">
                    <i class="el-icon-reading"></i>
                    <span slot="title">MyBook</span>
                </el-menu-item>


                <el-menu-item index="manage" @click="Link('manage')">
                    <i class="el-icon-s-tools"></i><span slot="title">Manage</span>
                </el-menu-item>

            </el-menu>


<!--            <div class="card">-->
<!--                 <div>-->
<!--                    <span>打破企业间壁垒，提供便捷的接入方式，实现不企业，不同品牌、不同类型间的家电的数据互联互通和数据协同</span>-->
<!--                </div>-->
<!--            </div>-->

        </el-col>


<!--         页面-->
          <el-col :span="23" >


              <router-view></router-view>


          </el-col>

      </el-row>



  </div>
</template>

<script>


export default {
  name: 'app',
  data() {
       return{
           rate:null
       }
    },
  methods:{

      Link(path){
          this.$router.push("/"+path)
      }

  },
    computed:{
        navIndex() {
            return this.$route.name;
        }
    }



}
</script>

<style>


    .card{

        background-color: white;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
        border-radius: 4px;
        display: inline-block;
        margin-right: 4%;
        margin-top: 20%;
        vertical-align: top;
    }
    .card span {
        font-size: 12px;
        color: deepskyblue;
        display: block;
        letter-spacing: 2px;
        padding: 30px 20px;
    }


</style>
