<template>
  <div class="">
      <div class="nav-breadcrumb-wrap">
        <div class="container">
            <nav class="nav-breadcrumb">
            <a href="/">Home</a>
            <!-- 插槽 -->
            <slot name="bread"></slot>
            <slot name="B"></slot>
            </nav>
        </div>
        </div>
        </div>

        
</template>

<script>
export default {
  name: '',
  data() { 
    return {

    }
  },
  props: {

  },
  components:{
  },
  mounted() {

  },
  methods:{

  },
watch:{

},
 }
</script>

<style>
 
</style>