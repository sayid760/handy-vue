<template>
  <main>
    <div class="ha-doc-content">
      <slot />
    </div>
  </main>
</template>

<script>
  export default {
    name: 'ha-doc-content',
    computed: {
      // currentPage() {
      //   const { path } = this.$route;
      //   if (path) {
      //     return path.split('/').slice(-1)[0];
      //   }
      //   return this.$route.name;
      // },
    }
  }
</script>

<style lang="scss">
  @import '../assets/style/var';

  main {
    min-width: 1200px;
    margin: 0 auto 15px;
    padding-top: 30px;
    overflow: hidden;
    // background: #f7f8fa;
    // &.document-quick-start .ha-doc-content{
    //   padding: 0 60px 140px 340px;
    // }
    .ha-doc-content {
      border-left: 1px solid #ebedf0;
      font-size: 16px;
      margin-left: -1px;
      min-height: 500px;
      overflow: hidden;
      padding: 0 408px 100px 240px;
      position: relative;
      @media (min-width: $ha-doc-row-max-width) {
        padding: 0 490px 100px 320px;
      }
      .card {
        margin-bottom: 24px;
        padding: 24px;
        background-color: #fff;
        border-radius: $ha-doc-border-radius;
        box-shadow: 0 8px 12px #ebedf0;
      }

      a {
        margin: 0 1px;
        color: $ha-doc-blue;
        -webkit-font-smoothing: auto;

        &:hover {
          color: darken($ha-doc-blue, 10%);
        }

        &:active {
          color: darken($ha-doc-blue, 20%);
        }
      }

      h1,
      h2,
      h3,
      h4,
      h5,
      h6 {
        color: $ha-doc-black;
        font-weight: normal;
        line-height: 1.5;

        &[id] {
          cursor: pointer;
        }
      }

      h1 {
        margin: 0 0 30px;
        font-size: 30px;
        cursor: default;
      }

      h2 {
        margin: 45px 0 20px;
        font-size: 22px;
      }

      h3 {
        margin-bottom: 16px;
        font-weight: 500;
        font-size: 18px;
      }

      h4 {
        margin: 24px 0 12px;
        font-weight: 500;
        font-size: 15px;
      }

      h5 {
        margin: 24px 0 12px;
        font-weight: 500;
        font-size: 14px;
      }

      p {
        color: $ha-doc-text-color;
        font-size: 14px;
        line-height: 26px;
      }
      code {
        position: relative;
        display: block;
        overflow-x: auto;
        color: #58727e;
        font-weight: 400;
        font-size: 13.4px;
        font-family: $ha-doc-code-font-family;
        line-height: 26px;
        white-space: pre-wrap;
        word-wrap: break-word;
        -webkit-font-smoothing: auto;
      }

      table {
        width: 100%;
        margin-top: 12px;
        color: $ha-doc-text-color;
        font-size: 13px;
        line-height: 1.5;
        border-collapse: collapse;

        th {
          padding: 8px 10px;
          font-weight: 500;
          text-align: left;

          &:first-child {
            padding-left: 0;
          }

          &:last-child {
            padding-right: 0;
          }
        }

        td {
          padding: 8px;
          border-top: 1px solid $ha-doc-code-background-color;

          &:first-child {
            padding-left: 0;

            // version tag
            code {
              margin: 0;
              padding: 2px 6px;
              color: $ha-doc-blue;
              font-weight: 500;
              font-size: 10px;
              background-color: fade($ha-doc-blue, 10%);
              border-radius: 20px;
            }
          }

          &:last-child {
            padding-right: 0;
          }
        }

        em {
          color: $ha-doc-green;
          font-size: 12.5px;
          font-family: $ha-doc-code-font-family;
          font-style: normal;
          -webkit-font-smoothing: auto;
        }
      }

      ul li,
      ol li {
        position: relative;
        margin: 5px 0 5px 10px;
        padding-left: 15px;
        color: $ha-doc-text-color;
        font-size: 14px;
        line-height: 26px;

        &::before {
          position: absolute;
          top: 0;
          left: 0;
          box-sizing: border-box;
          width: 6px;
          height: 6px;
          margin-top: 10px;
          border: 1px solid $ha-doc-dark-grey;
          border-radius: 50%;
          content: '';
        }
      }

      hr {
        margin: 30px 0;
        border: 0 none;
        border-top: 1px solid #eee;
      }

      p > code,
      li > code,
      table code {
        display: inline;
        margin: 2px 3px;
        padding: 2px 5px;
        font-size: 13px;
        font-family: inherit;
        word-break: keep-all;
        background-color: #f0f2f5;
        border-radius: 4px;
        -webkit-font-smoothing: antialiased;
      }

      p > code {
        font-size: 14px;
      }

      section {
        padding: 30px;
        overflow: hidden;
      }

      blockquote {
        margin: 20px 0 0;
        padding: 16px;
        color: rgba(52, 73, 94, 0.8);
        font-weight: 500;
        font-size: 14px;
        background-color: #ecf9ff;
        border-radius: $ha-doc-border-radius;
      }

      img {
        width: 100%;
        margin: 16px 0;
        border-radius: $ha-doc-border-radius;
      }

      &--changelog {
        strong {
          display: block;
          margin: 24px 0 12px;
          font-weight: 500;
          font-size: 15px;
        }

        h3 {
          + p code {
            margin: 0;
          }

          a {
            color: inherit;
            font-size: 20px;
          }
        }
      }
    }
  }
</style>
