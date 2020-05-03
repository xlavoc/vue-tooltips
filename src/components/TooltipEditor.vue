<template>
  <main class="tteditor">
    <h2>#{{ id }}: {{ name }}</h2>
    <article>
      <section class="edit">
        <div class="info">
          <span class="lang-prefix">PL</span><img src="@/assets/flag_PL.png" width="34" height="20">
          <div class="badge badge-ok m-t-1">completed</div>
          <div class="font-small">at 2020.04.25</div>
          <div class="section-bottom">
            <button>edit</button>
          </div>
        </div>
        <textarea v-model="lang[0].content" placeholder="put your text here"></textarea>
      </section>
      <section class="preview">
        <TooltipPreview :content="lang[0].content" />
      </section>
    </article>
    <hr>
    <article>
      <section class="edit">
        <div class="info">
          <span class="lang-prefix">DE</span><img src="@/assets/flag_DE.png" width="34" height="20">  
          <div class="badge badge-progress m-t-1">in edition</div>
          <div class="section-bottom">
            <button>save</button>
            <button>publish</button>
          </div>
        </div>
        <textarea v-model="lang[1].content" placeholder="put your text here"></textarea>
      </section>
      <section class="preview">
        <TooltipPreview :content="lang[1].content" />
      </section>
    </article>
    <hr>
    <article>
      <section class="edit">
        <div class="info">
          <span class="lang-prefix">EN</span><img src="@/assets/flag_UK.png" width="34" height="20">  
          <div class="badge badge-progress m-t-1"></div>
          <div class="section-bottom">
          </div>
        </div>
        copy translation from
        <select>
          <option value="PL">PL</option>
          <option value="DE">DE</option>
        </select>
        <button>OK</button>
      </section>
      <section class="preview">
      </section>
    </article>

  </main>
</template>

<script>
import TooltipPreview from "@/components/TooltipPreview"

export default {
  name: 'TooltipEditor',
  components: {
    TooltipPreview
  },
  data() {
    return {
      name: 'ttEditPriceMarkupMin',
      id: 101,
      lang: [
        { prefix: 'PL', status: 'completed', content:
        `<h3>Narzut minimalny</h3>
Służy do wyliczenia <i>ceny minimalnej</i> oferty,<br>
czyli <b>gwarantowanej ceny</b>, poniżej której Clipperon<br>
nie wystawi Twojego produktu na platformie Amazon.`},
        { prefix: 'DE', status: 'in edition', content:
        `<h3>Narzut minimalny</h3>
Służy do wyliczenia <i>ceny minimalnej</i> oferty,<br>
czyli <b>gwarantowanej ceny</b>, poniżej której Clipperon<br>
nie wystawi Twojego produktu na platformie Amazon.`}
      ]
    }
  }
}
</script>

<style lang="scss">

.tteditor article {
  display: flex;
  justify-content: center;
  //align-items: flex-start;

  section {
    width: 49vw;
  }
  .edit {
    display: flex;
    .info {
      display: inline-block;
      position: relative;
      padding: 0 .5rem;
      min-width: 100px;
      text-align: right;

      .section-bottom {
        position: absolute;
        bottom: 0;
        right: .5rem;
      }
      button {
        margin-top: .3rem;
      }
    }
    .lang-prefix {
      vertical-align: .2em;
      padding-right: .4em;
    }
    textarea {
      flex-grow: 2;
      min-height: 10rem;
    }
  }
}

</style>