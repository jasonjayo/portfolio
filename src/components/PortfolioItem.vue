<template>
  <article class="project">
    <header>
      <div class="project__header-logo">
        <img
          v-if="item.logoUrl"
          :src="item.imagesFolder + '/' + item.logoUrl"
          :alt="item.name"
        />
      </div>
      <div class="project__header-details">
        <div class="project__header-title">{{ item.name }}</div>
        <div class="project__header-date">
          {{ item.date }}<span class="material-icons">calendar_month</span>
        </div>
        <div class="project__header-link">
          <a :href="item.url" target="_blank"
            >Visit website<span class="material-icons">open_in_new</span></a
          >
        </div>
        <div class="project__header-stack">
          Made with
          <img
            src="/vue-logo.png"
            v-if="item.madeWith.indexOf('vue') > -1"
            title="Vue.js"
            alt="Made with Vue.js"
          />
          <img
            src="/sass-logo.png"
            v-if="item.madeWith.indexOf('sass') > -1"
            title="Sass"
            alt="Made with Sass"
          />
          <span v-if="item.madeWith.indexOf('wordpress') > -1">WordPress</span>
          <span v-if="item.madeWith.indexOf('pi') > -1">Raspberry Pi</span>
          <span v-if="item.madeWith.indexOf('readsb') > -1"
            ><a target="_blank" href="https://github.com/wiedehopf/readsb"
              >readsb</a
            ></span
          >
        </div>
      </div>
    </header>
    <div class="project__images">
      <figure
        class="project__image"
        :class="{ 'project__image--primary': image.primary }"
        v-for="image in item.images"
        :key="image.src"
      >
        <a :href="item.imagesFolder + '/' + image.src" target="_blank"
          ><img :src="item.imagesFolder + '/' + image.src"
        /></a>
        <figcaption>{{ image.caption }}</figcaption>
      </figure>
    </div>
    <div class="divider"></div>
    <div class="project__description">
      <slot name="description"></slot>
    </div>

    <div class="project__link">
      <a :href="item.url" target="_blank">Visit Site</a>
    </div>
  </article>
</template>
<style lang="scss">
.project {
  background: var(--grey);
  margin-bottom: 10em;
  header {
    background: var(--dark-grey);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 2em 4em;
    gap: 2em;
    flex-wrap: wrap;
  }
  &__header- {
    &details {
      border: 8px solid #ffffff;
      font-size: 1.1em;
      padding: 1.5em 2em;
    }
    &logo {
      flex-basis: 35%;
      flex-grow: 1;
      img {
        max-width: 100%;
        max-height: 110px;
      }
    }
    &title {
      font-weight: bold;
      font-size: 1.2em;
      margin-bottom: 1em;
    }
    &date,
    &link,
    &stack {
      color: #434343;
    }
    &link a {
      color: inherit;
      text-decoration: none;
    }
    &stack {
      margin-top: 1em;
      img {
        width: 30px;
        vertical-align: middle;
        margin: 0 0.25em;
      }
      span {
        &:not(:last-of-type) {
          &::after {
            content: ", ";
          }
        }
        a {
          color: inherit;
        }
      }
      img:first-of-type {
        margin-left: 0.5em;
      }
    }
  }
  &__images {
    display: flex;
    flex-wrap: wrap;
    gap: 4em;
    justify-content: center;
    margin: 4em;
    figcaption {
      background: #dee4ea;
      text-align: center;
      padding: 1em;
      flex-grow: 1;
    }
    h2 {
      margin-bottom: 1em;
    }
  }
  &__image {
    box-shadow: 0 0px 30px rgb(0 0 0 / 24%);
    display: flex;
    flex-flow: column;
    justify-content: center;
    img {
      width: 100%;
      display: block;
    }
    width: 325px;
    &--primary {
      width: 500px;
    }
  }
  &__description {
    text-align: justify;
    padding: 2em;

    & > div {
      display: flex;
      align-items: stretch;
      margin: 4em 0;
      background: #fff;
      &:not(:last-of-type) h3::after {
        content: " ";
        left: 50%;
        transform: translateX(-50%);
        width: 50px;
        background: #dee4ea;
        bottom: -80px;
        height: 110px;
        position: absolute;
      }
    }
    &-content {
      padding: 2em;
      p {
        background: #fff;
      }
      ul {
        margin: 1em 0;
      }
    }
    h3 {
      text-transform: uppercase;
      font-size: 2em;
      flex-basis: 30%;
      flex-shrink: 0;
      background: #dee4ea;
      padding: 0.25em 1em;
      display: flex;
      align-items: center;
      justify-content: center;
    }
  }
  &__link {
    background: #1b88db;
    color: #fff;
    a {
      color: #fff;
      display: block;
      text-align: center;
      text-decoration: none;
      text-transform: uppercase;
      padding: 0.75em;
      font-size: 1.75em;
      font-weight: 600;
    }
  }
  .divider {
    height: 10px;
    background: #dee4ea;
  }
}
@media (max-width: 1200px) {
  .project {
    &__description {
      & > div {
        flex-wrap: wrap;
      }
      h3::after {
        display: none;
      }
      h3 {
        flex-grow: 1;
      }
    }
  }
}
</style>

<script>
export default {
  props: ["item"],
};
</script>
