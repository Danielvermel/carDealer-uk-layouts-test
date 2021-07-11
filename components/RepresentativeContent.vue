<template>
    <section class="representative-banner">
        <div class="flexbox-container justify-content-between align-center">
            <p class="flexbox-item-9">
                <strong>Representative example:</strong> Borrowing £11,790.00 over 4 years with a representative APR of 7.9 %, an annual interest rate of 4.08 % (Fixed) 
                and a deposit of £500.00, the amount payable would be £273.59 per month, with a total cost of credit of £1,843.32 and a total amount payable 
                of £13,633.32.
            </p>
            <div class="flexbox-item-3">
                <button class="button-hidden px-3">
                    Hide breakdown 
                    <ArrowUpIcon class="button-hidden-arrow ml-3" />
                </button>
            </div>
        </div>
        <div class="flexbox-container justify-content-between mt-4">
            <button 
                class="flexbox-item-button pb-2" 
                :class="{
                    'active': active
                }"
                @click="active = !active"
            >
                Personal Contract Purchase
            </button>
            <button 
                class="flexbox-item-button pb-2"
                :class="{
                    'active': !active
                }"
                 @click="active = !active"
            >
                Hire Purchase
            </button>
        </div>

        <div class="flexbox-container">
            <FinanceCard title="48 monthly payments" text="£157.25" />
            <FinanceCard title="Cash price" text="£9,998.00" />
            <FinanceCard title="Customer deposit" text="£250.00" />
            <FinanceCard title="Amount of credit" text="£11,980.75" />
            <FinanceCard title="APR" text="7.9%" />
            <FinanceCard title="Term" text="48 months" />
            <FinanceCard title="Total amount payable" text="£12,163.72" />
            <FinanceCard title="Rate of interest (fixed)" text="4.08% PA" />
            <FinanceCard title="Annual mileage" text="8,000" />
            <FinanceCard title="Optional financial payment" text="£3,888.04" />

        </div>

    </section>
</template>

<script>
import ArrowUpIcon from 'vue-material-design-icons/ChevronUp.vue';

    export default {
    data() {
        return {
            active: true
        };
    },
      components: {
        ArrowUpIcon
        }

    }
</script>
<style scpoed lang="scss">
@import '~/assets/css/main.scss';

.representative-banner{
    background-color: $background-white-color;
    border-radius: $border-radius-lg;
    padding: 15px;
    border: 1px solid $border-grey-color;
    margin: 40px 30px 50px 0;
    font-family: -apple-system, BlinkMacSystemFont, sans-serif;

    .button-hidden {
        background-color: #FFFFFF;
        border-radius: $border-radius-lg;
        border: solid 1px #FFFFFF; 
        color: $text-grey-color;
        align-items: center;
        display: flex;
        justify-content: space-between;
        float: right;
        padding: 24px;
    }

    .button-hidden-arrow{
        background-color: $border-grey-color;
        color:#FFFFFF;
        border-radius: $border-radius-sm;
    }

    .flexbox-item-button {
        width: 50%;
        background-color: transparent;
        border-top: none;
        border-right: none;
        border-bottom: 1px solid $border-grey-color;
        border-left: none;
    }

    .active {
        border-bottom:  3px  solid $primary-color;
    }
    
    p {
        line-height: 24px;
        
    }
 }
</style>