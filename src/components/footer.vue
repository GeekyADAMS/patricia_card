<template>
    <div class="footer w100 mt-5 flex-col a-c">
        <h3 class="h3 g-medium w30 w80p-m mt-5 t-center milk">Anywhere  in the world, we've got you covered!.</h3>

        <p class="blt g-regular w60 w95p-m milk t-center mt-2" >
        Our services are available to you anywhere, anytime. Each Patricia system is built for you and tailored to suit your need. That’s how we plan to change the world. By joining Patricia, you help to make this dream come true and change the world with us.
        </p>

        <img src="@/assets/img/illustrations/map 1.png" alt="" class="mt-3">

        <div class="line w100 mt-5 mb-3"></div>

        <div class="flex-row wrap w100">

        <section class="footer-links flex-row space-btw flex-wrap wrap s-ml-n2" style="max-width: 100vw;">

            <select name="" id="" class="b2t g-medium milk">
                <option value="NG">NG Nigeria [English]</option>
                <option value="SP">SP Spain [Spanish]</option>
                <option value="GE">GER Germany [German]</option>
            </select>

            <div class="flex-row flex-col-m flex-wrap wrap space-btw w50 flex-wrap wrap s-mt-5" style="max-width: 100vw;">
                <div v-for="(linkTextItem, index) in footerLinks" :key="index" class="flex-col link-col poppins s-mt-1">
                <h4 class="blt g-medium milk">{{linkTextItem.LinkHead}}</h4>
                <ul class="g-regular b2t milk">
                    <li v-for="link in linkTextItem.linkList" :key="link"><router-link class="g-regular b2t milk" to="/">{{link.text}}</router-link></li>
                </ul>
                </div>
            </div>
        </section>
        </div>

        <div class="mt-2 flex-col w100 ml-13 s-ml-8">
        <img src="@/assets/img/logo/logo 1.png" alt="" style="width: 8rem; height: 1.7em;">
        <p class="b2t g-regular milk mt-p5">
            &copy; {{copyrightYear}} Patricia
        </p>
        </div>
    </div>
</template>

<script>
export default {
  data () {
    return {
      footerLinks: [
        { LinkHead: 'Products', linkList: [{ text: 'Patricia Card', link: '/' }, { text: 'BTC', link: '/' }, { text: 'Perfect Money', link: '/' }] },
        { LinkHead: 'Company', linkList: [{ text: 'Careers', link: '/' }, { text: 'FAQs', link: '/' }, { text: 'Term of use', link: '/' }, { text: 'Privacy policy', link: '/' }, { text: 'Anti-money laundering policy', link: '/' }] },
        { LinkHead: 'Social', linkList: [{ text: 'Blog', link: '/' }, { text: 'Twitter', link: '/' }, { text: 'Facebook', link: '/' }] }
      ],
      copyrightYear: ''
    }
  },
  created () {
    this.copyrightYear = new Date().getFullYear()
  }
}
</script>

<style scoped>
.footer-links{
    padding: 0 6rem 3rem 6rem;
    width: 85vw;
    flex-wrap: wrap;
}

.link-cols-wrap{
    width: 46.5vw;
    flex-wrap: wrap;
}
.link-col>h4{
    margin-bottom: 1.2rem;
}
.link-col>ul>li{
    list-style-type: none;
    cursor: pointer;
    line-height: 1.85rem;
    margin-left: -1rem;
}
.link-col>ul>li:hover{
    opacity: .9;
}

select{
    min-width: 20vw;
    height: 2.5rem;
    border: 1px solid whitesmoke;
    border-radius: 5px;
    background: transparent;
}
</style>
