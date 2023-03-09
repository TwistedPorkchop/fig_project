<script>
    import { loadScript } from "@paypal/paypal-js";

    async function test(){
        let paypal;
        try {
            paypal = await loadScript({ "client-id": "test" });
        } catch (error) {
            console.error("failed to load the PayPal JS SDK script", error);
        }

        if (paypal) {
            try {
                await paypal.Buttons().render("#paypal");
            } catch (error) {
                console.error("failed to render the PayPal Buttons", error);
            }

            loadScript({ "client-id": "test" })
            .then((paypal) => {
                paypal
                    .Buttons()
                    .render("#paypal")
                    .catch((error) => {
                        console.error("failed to render the PayPal Buttons", error);
                    });
            })
            .catch((error) => {
                console.error("failed to load the PayPal JS SDK script", error);
            });
        }
    }

</script>

<div id="paypal">
    POPOUT
</div>

<button class="item" on:click={console.log(test())}>This is an Item</button>

<style>
    .item{
    padding: 10px;
    background-color: purple;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
</style>