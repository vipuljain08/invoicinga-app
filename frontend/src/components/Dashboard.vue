<template>
    <div class="container">
        <Header v-bind:user="user"/>
        <template v-if="this.isactive=='create'">
            <CreateInvoice />
        </template>
        <template v-else>
            <ViewInvoices />
        </template>
    </div>
</template>

<script>
import Header from "./Header"
import CreateInvoice from "./CreateInvoice"
import ViewInvoices from "./ViewInvoices"

export default {
    name: "Dashboard",
    components: {
        Header,
        CreateInvoice,
        ViewInvoices
    },
    data() {
        return {
            isactive: 'create',
            title: 'Invoicing App',
            user: null
        }
    },
    mounted(){
        this.user = JSON.parse(localStorage.getItem("user"))
    }
}
</script>