<template>
    <div class="mockup-phone">
        <div class="camera"></div> 
        <div class="display">
            <div class="artboard artboard-demo phone-1 bg-white">
                <PaymentStatusToast v-if="false"></PaymentStatusToast>
                <div class="container mx-auto w-full">
                    <div class="">
                        <img src="@/assets/logo.png" alt="" class="w-1/3 mx-auto qiwi-logo">
                    </div>
                    <div class="rounded-2xl p-3">
                        <div class="">
                            <form @submit="processPayment()">
                                <div class="payment-card bg-orange-600 rounded-xl pb-2">
                                    <div class="grid grid-cols-1 p-2 px-4">
                                        <label for="" class="label">
                                            <span class="label-text text-orange-50 font-medium">Номер карты</span>
                                            <span v-if="cardType" class="label-text-alt text-orange-50 font-bold">{{ cardType }}</span>
                                        </label>
                                        <input v-model="cardNumber" @input="detectCardType" type="text" class="input w-full bg-orange-500 text-orange-50 font-medium">
                                    </div>
                                    <div class="grid grid-cols-2 p-2 pt-0 px-4">
                                        <div class="mr-2">
                                            <label for="" class="label mr-4">
                                                <span class="label-text text-orange-50 font-medium">ММ\ГГ</span>
                                            </label>
                                            <input v-model="cardExpire" type="text" class="input w-full bg-orange-500 text-orange-50 font-medium">
                                        </div>
                                        <div class="ml-2">
                                            <label for="" class="label">
                                                <span class="label-text text-orange-50 font-medium">CVC/CVV</span>
                                            </label>
                                            <input v-model="cardCVC" type="number" class="input w-full bg-orange-500 text-orange-50 font-medium">
                                        </div>
                                    </div>
                                </div>
                                <label for="" class="label mt-2">
                                    <span class="label-text font-medium">Сумма</span>
                                    <span class="label-text-alt font-bold">РУБ</span>
                                </label>
                                <input v-model="amount" type="text" class="input w-full bg-slate-100 input-bordered text-orange-50 font-medium">
                                <button type="submit" class="btn btn-lg rounded-full w-full block mt-4 mx-auto btn-neutral">Оплатить</button>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import PaymentStatusToast from './PaymentStatusToast.vue';

export default {
    data() {
        return {
            cardNumber: null,
            cardType: "",
            cardExpire: "",
            cardCVC: "",
            amount: null
        };
    },
    methods: {
        detectCardType() {
            const visaPattern = /^4[0-9]{12}(?:[0-9]{3})?$/;
            const mirPattern = /^2[0-9]{15}$/;
            const mastercardPattern = /^5[1-5][0-9]{14}$/;
            if (visaPattern.test(this.cardNumber)) {
                this.cardType = "Visa";
            }
            else if (mirPattern.test(this.cardNumber)) {
                this.cardType = "Mir";
            }
            else if (mastercardPattern.test(this.cardNumber)) {
                this.cardType = "MasterCard";
            }
            else {
                this.cardType = "";
            }
        },
        processPayment() {
            console.log(this.cardNumber);
            console.log(this.amount);
            console.log(this.cardExpire);
            console.log(this.cardCVC);
            return false;
        }
    },
    components: { PaymentStatusToast }
};
</script>

<style>
.mockup-phone {
    position: absolute;
    top:50%;
    left:50%;
    transform: translate(-50%, -50%);
}
.qiwi-logo {
    filter: invert(.8)
}
</style>