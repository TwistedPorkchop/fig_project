<script>
    import { loadScript } from "@paypal/paypal-js";

    async function test(){
        let paypal_sdk;
        try {
            paypal_sdk = await loadScript({ "client-id": "test", "data-namespace": "paypal_sdk" });
        } catch (error) {
            console.error("failed to load the PayPal JS SDK script", error);
        }

        if (paypal_sdk) {
            try {
                await paypal_sdk.Buttons().render("#paypal");
            } catch (error) {
                console.error("failed to render the PayPal Buttons", error);
            }
        }
    }

</script>

<div id="paypal">
    <button class="item" on:click={test()}>This is an Item</button>
</div>



<style>
    .item{
    padding: 10px;
    background-color: purple;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
#paypal{
    width: 100px;
    height: 100px;
}
</style>
