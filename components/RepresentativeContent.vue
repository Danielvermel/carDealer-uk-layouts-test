<template>
    <section class="representative-banner my-5">
        <div class="flexbox-container justify-content-between align-center">
            <p class=" flexbox-item-md-12 flexbox-item-lg-9">
                <strong>Representative example:</strong> Borrowing £11,790.00 over 4 years with a representative APR of 7.9 %, an annual interest rate of 4.08 % (Fixed) 
                and a deposit of £500.00, the amount payable would be £273.59 per month, with a total cost of credit of £1,843.32 and a total amount payable 
                of £13,633.32.
            </p>
            <div class="flexbox-item-md-12 flexbox-item-lg-3">
                <button class="button-hidden px-3">
                         <span v-if="!hideButtonActive">Hide breakdown </span>
                        <ArrowUpIcon v-if="!hideButtonActive" @click="hideButtonActive = !hideButtonActive" class="button-hidden-arrow ml-3" />
                        <span v-if="hideButtonActive">Show breakdown </span>
                        <ArrowDownIcon v-if="hideButtonActive" @click="hideButtonActive = !hideButtonActive" class="button-hidden-arrow ml-3" />        
                </button>
            </div>
        </div>
        <div v-if="!hideButtonActive" class="flexbox-container justify-content-between mt-4">
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

        <div v-if="!hideButtonActive" class="flexbox-container mt-3">
            <FinanceCard title="48 monthly payments" text="£157.25"  class="px-1 pb-3" />
            <FinanceCard title="Cash price" text="£9,998.00" class="px-1 pb-3"/>
            <FinanceCard title="Customer deposit" text="£250.00" class="px-1 pb-3"/>
            <FinanceCard title="Amount of credit" text="£11,980.75" class="px-1 pb-3"/>
            <FinanceCard title="APR" text="7.9%" class="px-1 pb-3"/>
            <FinanceCard title="Term" text="48 months" class="px-1 pb-3"/>
            <FinanceCard title="Total amount payable" text="£12,163.72" class="px-1 pb-3"/>
            <FinanceCard title="Rate of interest (fixed)" text="4.08% PA" class="px-1 pb-3"/>
            <FinanceCard title="Annual mileage" text="8,000" class="px-1 pb-3"/>
            <FinanceCard title="Optional financial payment" text="£3,888.04" class="px-1 pb-3"/>
        </div>

    </section>
</template>

<script>
import ArrowUpIcon from 'vue-material-design-icons/ChevronUp.vue';
import ArrowDownIcon from 'vue-material-design-icons/ChevronDown.vue';

    export default {
    data() {
        return {
            active: true,
            hideButtonActive: false
        };
    },
      components: {
        ArrowUpIcon,
        ArrowDownIcon
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
        padding: 20px 24px;

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