<template> 
    <div class="mx-5">
        <div class="flexbox-container justify-content-between my-5">
            <strong>Filters</strong> 
            <button class="button-reset">Reset</button>
        </div>
        <div>
            <span>Brand </span>
            <ul>
                <li>
                    <span class="float-left">Make</span> 
                    <span class="float-right">+</span>
                </li>
                <li>
                    <span class="float-left">Model</span> 
                    <span class="float-right">+</span>
                </li>
            </ul>

            <span>Specification</span>
            <ul>
                <li>
                    <span class="float-left">Fuel type</span> 
                    <span class="float-right">+</span>
                </li>
                <li>
                    <span class="float-left">Body type</span> 
                    <span class="float-right">+</span>
                </li>
                <li>
                    <span class="float-left">Transmission</span> 
                    <span class="float-right">+</span>
                </li>
                <li>
                    <span class="float-left">Engine size</span> 
                    <span class="float-right">+</span>
                </li>
                <li>
                    <span class="float-left">Mileage</span> 
                    <span class="float-right">+</span>
                </li>
                <li>
                    <span class="float-left">Colour</span> 
                    <span class="float-right">+</span>
                </li>
                <li>
                    <span class="float-left">Doors</span> 
                    <span class="float-right">+</span>
                </li>
                <li>
                    <span class="float-left">Seats</span> 
                    <span class="float-right">+</span>
                </li>
                <li>
                    <span class="float-left">Features</span> 
                    <span class="float-right">+</span>
                </li>
            </ul>
        </div>
    </div>

</template>

<style scoped>
.flexbox-container {
    display: flex;
    align-items: center;
}
.button-reset {
    color: #F87B7B;
    background-color: rgb(248 123 123 / 15%);
    border-radius: 16px;
    padding: 6px 7px;
    border: none;
}

</style>