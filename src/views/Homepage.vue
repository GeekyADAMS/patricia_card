<template>
    <div>
      <div class="hero h100 flex-row flex-col-m">
        <div class="hero-texts w50 s-w100 h100p flex-col a-c">
          <div class="flex-col">
            <h1 class="h1 poppins p-color t-left">Patricia Card</h1>
            <p class="g-regular darkTxt mt-5 blt t-left h-Caption1 w55p">
              A new kind of debit card designed by Patricia, <br v-if="!mobile">not a bank
            </p>
            <button class="fit g-medium white cta-btn p-bg point mt-3 blt round-2 anime-btn-1 btn1">Apply to get card now</button>
          </div>
        </div>

        <div class="hero-illustration w50 s-w100 h100p flex-col a-c">

          <div class="flex-row mt-2 ml-n2">
            <div class="flip-card point f1">
              <div class="flip-card-inner">
                <div class="flip-card-front ff1">
                </div>
                <div class="flip-card-back fb1">
                </div>
              </div>
            </div>

            <div class="flip-card point bounce-2 f2">
              <div class="flip-card-inner">
                <div class="flip-card-front ff2">
                </div>
                <div class="flip-card-back  fb2">
                </div>
              </div>
            </div>

            <div class="flip-card point bounce-2 f3">
              <div class="flip-card-inner">
                <div class="flip-card-front ff3">
                </div>
                <div class="flip-card-back  fb3">
                </div>
              </div>
            </div>
          </div>
        </div>

      </div>

      <div class="flex-row flex-col-m w100 a-c mb-2 s-mt-5">
        <div class="flex-col w25 s-w80 ml-1 mr-1 mt-2">
          <p class="title g-medium green">Simple and Rewarding</p>
          <p class="mt-2 b2t g-light">With Patricia card, online paymets just got easier and simpler to acheive. Earn while you spend! Cryptoback™ gets you up to 1.5% back in BTC on all in-store purchases</p>
        </div>

        <div class="flex-col w25 s-w80 ml-1 mr-1 mt-2">
          <p class="title g-medium green">Secure and Safe</p>
          <p class="mt-2 b2t g-light">Our 2-Factor Authentication (2FA) and Device Authorisation makes it possible and ensures that only you can access your account making your transactions safe and secured.</p>
        </div>

        <div class="flex-col w25 s-w80 ml-1 mr-1 mt-2">
          <p class="title g-medium green">Certified and Transparent</p>
          <p class="mt-2 b2t g-light">Keep track of your spending and budget with the instant in-app alerts for each account. Patricia is a licensed e-money issuer with the FCA</p>
        </div>
      </div>

      <div class="flex-row flex-col-m w100 services mt-5 a-c">
        <div class="left w60 flex-col ml-8 mt-3 s-ml-1p5 w90-m">
          <h3 class="h3 g-medium">Patricia Card Benefits</h3>
          <span class="mt-3"></span>
          <div class="flex-row mt-p5" v-for="(benefit, index) in card_benefits" :key="index">
            <i style="height: 10px; width: 10px; border-radius: 100%;background: #0050AF;" class="mr-1"></i>
            <p class="subtext g-regular" style="color: #0050AF; max-width: 70%;">{{benefit}}</p>
          </div>
        </div>

        <img src="@/assets/img/backgrounds/Patricia.png" alt="" class="right mt-3" v-if="!mobile">
      </div>

      <div class="hero h100 flex-row flex-col-m">
        <div class="hero-texts w50 s-w100 h100p flex-col a-c">
          <div class="flex-col w60p w90-m">
            <h3 class="h3 poppins p-color t-left">Get to use Patricia Card<br>today!</h3>
            <p class="g-regular darkTxt mt-5 blt t-left h-Caption1 w55p">
              You can apply for Patricia Card in the Patricia app on your device and start using it right away or you can apply by clicking the button below
            </p>
            <button class="fit g-medium white cta-btn p-bg point mt-3 blt round-2 anime-btn-1 btn1">Get card now</button>
          </div>
        </div>

        <div class="w50 s-w100 h100p flex-col a-c">
          <div class="flex-row a-c">
            <img src="@/assets/img/mockups/iPhone X Side View 1.png" alt="" data-aos="fade-right">
            <img src="@/assets/img/mockups/Frame 14.png" alt="" data-aos="fade-left">
          </div>

        </div>

      </div>

      <div class="hero h80 flex-row flex-col-m mb-2">

        <div class="w50 s-w100 h100p flex-col a-c" v-if="!mobile">
          <div class="flex-col a-c w70p h80p" v-for="(item, index) in useCases" :key="index">
            <img style="" :src="'/img/illustrations/'+item.illustration" alt="" data-aos="fade-right" v-if="item.active && !mobile">
          </div>
        </div>

        <div class="card-use-contain w50 w100-m h100p flex-col a-c">
          <div class="flex-col a-n-c w100-m">
            <h2 class="h3 poppins p-color t-left">Spend with <br>confidence</h2>

            <ul class="flex-row ml-np1 mt-2 w100-m">
              <li v-for="(use, index) in useCases" :key="index" style="list-style-type: none;" :class="{'g-medium b1t mr-3 s-mr-1p5 point': true, active: use.active, 'non-active': !use.active}" ref="index" @click="activate(index)">{{use.label}}</li>
            </ul>

            <div v-for="(use, index) in useCases" :key="index" class="w55p mt-4">
              <p class="g-regular blt t-left h-Caption1" v-if="use.active" style="max-width: 450px" v-html="use.description">
              </p>
            </div>
          </div>
        </div>

      </div>

    <div class="flex-row flex-col-m a-c">
        <div class="w70 flex-col a-c w100p-m m-margin">
          <div class="flex-col a-n-c w70p w100p-m mt-5">
            <h2 class="h g-bold p-color">Frequently Asked Questions [FAQ's]</h2>

            <p class="b2t g-regular mt-2 mb-3">We have answered these frequent questions <br v-if="mobile">intending and<br v-if="!mobile"> registered users ask more often.</p>

            <div class="faqs flex-col w80p w90-m mt-1" v-for="(faq, index) in FAQs" :key="index">
              <div class="flex-col">
                <div class="flex-row">
                  <span class="w85p quest darkTxt blt g-regular">{{faq.Question}}</span>
                  <span class="w15p sign t-center h4 g-sBold no-select point" @click="toggleDetails(index)">{{faq.expandedSign}}</span>
                </div>
                <span class="answer-slot w85p w100p-m b2t g-regular" v-if="faq.active">
                {{faq.Answer}}
                </span>
              </div>
            </div>
            <p class="g-regular subtext mt-2">Have more questions? <router-link to="/" class="g-medium no-deco">Proceed</router-link></p>
          </div>
        </div>

        <div class="left2 w30 flex-col a-c" v-if="!mobile">
          <img src="@/assets/img/illustrations/Frame 16.png" alt="" style="width: 15rem; height: 22rem;" class="mr-5 q-illus">
        </div>

      </div>

      <foot/>
    </div>

</template>

<script>
import foot from '@/components/footer'

export default {
  components: {
    foot
  },
  data () {
    return {
      card_benefits: [
        'Use you Patricia Card for online transactions.',
        'Earn Bitcoin rewards in every online transaction done using the Patricia card.',
        'Spend earned rewards in real life.',
        'Make withdrawals from your BTC wallet or with POS and ATM’s across 4 million countries.',
        'No fees or hidden charges.',
        'Avoid unnecessary bank charges and deductions when paying abroad in local currencies.',
        'With Patricia Card Monthly Installments, you can buy cryptocurrencies and pay for it with interest-free monthly payments. Your monthly installment appears right alongside your everyday Patricia Card purchases.',
        'Receive instant alerts and get to know more about your transactions.'
      ],
      FAQs: [
        {
          Question: 'How do I get a card?',
          Answer: 'The card and delivery are free of charge. There is a monthly card management fee of £1.00/€1.20/$1.50 to cover administration and operational costs. Please check our fees and limits page for a full breakdown.',
          active: false,
          expandedSign: '+'
        },
        {
          Question: 'How much is the card?',
          Answer: 'Absolutely free for order and delivery. No hidden charges.',
          active: false,
          expandedSign: '+'
        },
        {
          Question: 'How do I fund my card?',
          Answer: 'Add funds to your Patricia wallet via bank transfer, credit or debit card or using your crypto.',
          active: false,
          expandedSign: '+'
        },
        {
          Question: 'Where can I use my card?',
          Answer: 'Anywhere Visa is accepted. That means online and in shops, bars, restaurants, public transport and ATMs around the world.',
          active: false,
          expandedSign: '+'
        }
      ],
      useCases: [
        {
          name: 'Online',
          label: 'Online Transaction',
          description: 'Transfer money from you bitcoin wallet,<br v-if="mobile"> pay for online purchases, transfer funds to <br v-if="mobile">other other banks, make utility payments <br v-if="mobile">and so much more..',
          illustration: 'ONLINE.png',
          active: true
        },
        {
          name: 'ATM',
          label: 'ATM Withdrawal',
          description: 'Make cash withdrawal from any bank ATM,<br v-if="mobile"> both home and abroad.',
          illustration: 'ATM.png',
          active: false
        },
        {
          name: 'POS',
          label: 'POS Payment',
          description: 'Pay for items using POS machines and <br v-if="mobile">make cash withdrawals at ease.',
          illustration: 'POS.png',
          active: false
        }
      ],
      mobile: false
    }
  },
  methods: {
    activate (index) {
      this.useCases.map(function (element) {
        element.active = false
        return element.active
      })

      this.useCases[index].active = true
    },
    toggleDetails (index) {
      if (!this.FAQs[index].active) {
        this.FAQs.map(function (element) {
          element.active = false
          element.expandedSign = '+'
          return element.active
        })
        this.FAQs[index].active = true
        this.FAQs[index].expandedSign = 'x'
      } else {
        this.FAQs[index].active = false
        this.FAQs[index].expandedSign = '+'
      }
    }
  },
  created () {
    // var route = this.$router.currentRoute.name
    if (window.innerWidth < 480) {
      this.mobile = true
    }
  }
}
</script>

<style scoped>
  @import url(~@/assets/styles/Homepage.css);
</style>
