<template>
    <div class="container mx-auto mt-12 w-full md:w-1/3">
        <div class="rounded-2xl p-10 bg-white shadow-2xl shadow-slate-200">
            <div class="">
                <form action="" class="">
                    <div class="payment-card bg-orange-600 rounded-xl pt-6 pb-6">
                        <div class="grid grid-cols-1 p-2 px-4">
                            <label for="" class="label">
                                <span class="label-text text-orange-50 font-medium">Номер карты</span>
                                <span class="label-text-alt text-orange-50 font-bold">MasterCard</span>
                            </label>
                            <input type="text" class="input w-full bg-orange-500 text-orange-50 font-medium">
                        </div>
                        <div class="grid grid-cols-3 p-2 px-4">
                            <div>
                                <label for="" class="label mr-4">
                                    <span class="label-text text-orange-50 font-medium">ММ\ГГ</span>
                                </label>
                                <input type="text" class="input w-full bg-orange-500 text-orange-50 font-medium mr-4">
                            </div>
                            <div>
                                <label for="" class="label">
                                    <span class="label-text text-orange-50 font-medium ml-4">CVC/CVV</span>
                                </label>
                                <input type="text" class="input w-full bg-orange-500 text-orange-50 font-medium ml-4">
                            </div>
                        </div>
                    </div>
                    <button type="submit" class="btn btn-lg w-1/2 block mt-9 mx-auto btn-neutral">Оплатить</button>
                </form>
            </div>
        </div>
    </div>
</template>