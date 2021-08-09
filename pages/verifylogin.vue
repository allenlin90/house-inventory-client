<template>
    <v-container> checking {{ auth }} login process </v-container>
</template>

<script>
export default {
    data() {
        return {
            line: {
                returnedState: "",
                code: "",
            },
            auth: "",
        };
    },
    methods: {
        createQueryString(options = {}) {
            if (Object.keys(options).length) {
                const results = Object.entries(options).reduce(
                    (string, entry) => {
                        if (string) {
                            string += `&${entry[0]}=${entry[1]}`;
                        } else {
                            string += `${entry[0]}=${entry[1]}`;
                        }
                        return string;
                    },
                    ""
                );
                return results;
            }
        },
        parseJwt(token) {
            var base64Url = token.split(".")[1];
            var base64 = base64Url.replace(/-/g, "+").replace(/_/g, "/");
            var jsonPayload = decodeURIComponent(
                atob(base64)
                    .split("")
                    .map(function (c) {
                        return (
                            "%" +
                            ("00" + c.charCodeAt(0).toString(16)).slice(-2)
                        );
                    })
                    .join("")
            );
            return JSON.parse(jsonPayload);
        },
        getParameterByName(name, url = window.location.href) {
            name = name.replace(/[\[\]]/g, "\\$&");
            var regex = new RegExp("[?&]" + name + "(=([^&#]*)|&|#|$)"),
                results = regex.exec(url);
            if (!results) return null;
            if (!results[2]) return "";
            return decodeURIComponent(results[2].replace(/\+/g, " "));
        },
    },
    async mounted() {
        this.line.code = this.getParameterByName("code");
        this.line.returnedState = this.getParameterByName("state");
        if (this.line.code && this.line.returnedState) {
            this.auth = "LINE";
            try {
                const response = await this.$axios("/auth/line", {
                    method: "POST",
                    headers: { "content-type": "application/json" },
                    data: {
                        code: this.line.code,
                        returnedState: this.line.returnedState,
                    },
                });
                console.log(response);
            } catch (error) {
                console.log(error);
            }
        }
    },
};
</script>