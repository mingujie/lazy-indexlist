<template>
  <div class="lazy-indexlist">
    <div class="lazy-indexlist-search" ref="search">
      <div class="search-wrap">
        <div class="bar bar-header item-input-inset">
          <label class="item-input-wrapper">
            <i class="icon ion-ios-search placeholder-icon"></i>
              <input type="search" :placeholder="searchPlaceholder" v-model="searchKeyword">
          </label>
          <button class="button button-clear button-positive"
            @click='onCancel()'>
          </button>
        </div>
      </div>
    </div>
    <div class="lazy-indexlist-content" ref="content">
      <slot></slot>
    </div>
    <div class="lazy-indexlist-nav" ref="nav">
      <ul class="lazy-indexlist-navlist">
        <li class="lazy-indexlist-navitem"></li>
      </ul>
    </div>
    <div class='lazy-search-results' ref="searchResults" v-if="searchKeyword !== ''">
    </div>
  </div>
</template>

<script type="text/babel">
  export default {
    name: 'lazy-indexlist',

    props: {
      contentHeight: Number,
      showSearch: {
        type: Boolean,
        default: true
      },
      showNav:{
        type: Boolean,
        default: true        
      },
      navPosition: {
        type: String,
        default: 'right'
      },
      searchPlaceholder: {
        type: String,
        default: '搜索英雄'
      },
      cancelText: {
        type: String,
        default: '取消'
      },
      searchKeyword: {
        type: String,
        default: ''
      },
      searchError: {
        type: String,
        default: '没有找到与'+ this.searchKeyword +'相关的内容!'
      }
    },

    data() {
      return {
      }
    },

    watch: {

    },

    methods: {
      init() {

      },
      onCancel(keyword){

      }

    },

    mounted() {

    }
  };
</script>

<style lang="scss">
  .bar {
      border: none;
      background-image: linear-gradient(0deg, #ddd, #ddd 50%, transparent 50%);
      background-position: bottom;
      background-size: 100% 1px;
      background-repeat: no-repeat;
  }
  .lazy-indexlist-search {
    width: 100%;
    position: fixed;
    z-index: 2;
    .item-input-inset{
      display: flex;
      align-items: center;
      position: relative;
      overflow: hidden;
      padding: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,.15);
    }
  }
  .item-input-wrapper {
    display: flex;
    flex: 1 0;
    align-items: center;
    border-radius: 4px;
    padding-right: 8px;
    padding-left: 8px;
    background: #eee;
  }
</style>