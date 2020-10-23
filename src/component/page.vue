<template>
  <div>
    <div v-for="(item,index) in list" :ref="setItemRef" :key="index">
      {{item}}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return{
      list: [1,2,3],
      itemRefs: []
    }
  },
  methods: {
    setItemRef(el) {
      this.itemRefs.push(el)
    }
  },
  beforeUpdate(){
    this.itemRefs = []
  },
  updated(){
    console.log(this.itemRefs)
  }
}
</script>

<style>

</style>