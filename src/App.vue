<template>
  <h2 v-if="num === 0">The number is zero</h2>
  <h2 v-else-if="num < 0">The number is negative</h2>
  <h2 v-else-if="num > 0">The number is positive</h2>
  <h2 v-else >Not a number</h2>

  <template v-if="display">
  <h2>Vishwas</h2>
  <h2>Codevolution</h2>
  <h2>Vue</h2>
  </template>

  <h2 v-show="showElement">Using v-show</h2>
  <h2 v-if="showElement">Using v-if</h2>
  
 
  <h2 :id="headingId"> Heading </h2>
  <button :disabled="isDisabled">Bind</button>
  <h2 class="underline">Underlined text</h2>
  <h2 class="underline" :class="status">Status</h2>
  <h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 :class="isSoldout ? 'sold-out' : 'new' ">Soldout? movie</h2>
  <h2 :class="['new', 'promoted']">Newly promoted movie</h2>
  <h2 :class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Array conditional movie</h2>
  <h2 :class="{
    'promoted': isPromoted,
    new: !isPromoted,
    'sold-out': isSoldout
    }">Objetct conditional movie</h2>

    <h2 :style="{
      color: highlightColor,
      fontSize: headerSize + 'px',
      padding: '20px'
    }">Inline Style</h2>
    <h2 :style="headerStyleObject">Style Object</h2>

    <div :style="[baseStyleObject, successStyleObject]">Success Style</div>
    <div :style="[baseStyleObject, dangerStyleObject]">Danger Style</div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      num: 5,
      display: true,
      showElement: false,
      headingId: 'heading',
      isDisabled: false,
      status: 'success',
      isPromoted: true,
      isSoldout: true,
      highlightColor: 'orange',
      headerSize: 50,
      headerStyleObject: {
        color: 'orange',
        fontSize: '50px',
        padding: '20px',
      },
      baseStyleObject: {
        fontSize: '50px',
        padding: '10px',
      },
      successStyleObject: {
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green',
        padding: '20px',
      },
      dangerStyleObject: {
        color: 'darkred',
        backgroundColor: 'red',
        border: '1px solid darkred',
        padding: '20px',
      },
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: olivedrab;
}

.sold-out {
  color: red;
}

</style>
