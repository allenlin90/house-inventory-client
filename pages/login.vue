<template>
    <v-container>
        <v-row justify="center" align="center">
            <v-col cols="12" sm="8" md="6">
                <v-btn :href="lineLoginURL">LINE Login</v-btn>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    data() {
        return {
            line: {
                clientId: "1656295115",
                redirectUri: "http%3A%2F%2Flocalhost%3A3000%2Fverifylogin",
                stateParam: "",
                scope: `openid%20profile`,
                nonce: "",
            },
        };
    },
    computed: {
        lineLoginURL() {
            let URL = `https://access.line.me/oauth2/v2.1/authorize?`;
            URL += `response_type=code`;
            URL += `&client_id=${this.line.clientId}`;
            URL += `&redirect_uri=${this.line.redirectUri}`;
            URL += `&state=${this.line.stateParam}`;
            URL += `&scope=${this.line.scope}`;
            URL += `&nonce=${this.line.nonce}`;
            return URL;
        },
    },
    methods: {
        async getLineLoginParams() {
            try {
                const response = await this.$axios.post("/auth/line/params");
                if (response.status === 200) {
                    const { lineStateParam, lineNonce } = response.data;
                    this.line.stateParam = lineStateParam;
                    this.line.nonce = lineNonce;
                }
            } catch (error) {
                console.log(error);
            }
        },
    },
    async mounted() {
        await this.getLineLoginParams();
    },
};
</script>