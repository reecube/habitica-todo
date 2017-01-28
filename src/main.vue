<template>

    <!-- App -->
    <div id="app">

        <!-- Statusbar -->
        <f7-statusbar></f7-statusbar>

        <!-- Main Views -->
        <f7-views>
            <f7-view id="main-view" navbar-through :dynamic-navbar="true" main>

                <!-- Navbar -->
                <f7-navbar>
                    <f7-nav-center sliding>{{ title }}</f7-nav-center>
                </f7-navbar>

                <!-- Pages -->
                <f7-pages>
                    <f7-page>
                        <f7-list form>
                            <f7-list-item>
                                <f7-label>Benutzer-ID</f7-label>
                                <f7-input name="user-id" type="text"
                                          placeholder="Benutzer-ID" v-model="auth.userid"></f7-input>
                            </f7-list-item>
                            <f7-list-item>
                                <f7-label>API-Token</f7-label>
                                <f7-input name="api-token" type="text"
                                          placeholder="API-Token" v-model="auth.apitoken"></f7-input>
                            </f7-list-item>
                            <f7-list-item v-if="error && error.length">
                                <f7-label style="color: #f00; font-size: 0.7em;">{{ error }}</f7-label>
                            </f7-list-item>
                        </f7-list>
                        <f7-list>
                            <f7-list-button @click="onLogin" title="Einloggen"></f7-list-button>
                        </f7-list>
                    </f7-page>
                </f7-pages>
            </f7-view>
        </f7-views>
    </div>
</template>

<script>
    export default {
        methods: {
            onLogin: function (e) {
                e.preventDefault();

                this.$data.error = null;

                const auth = {
                    userid: this.$data.auth.userid,
                    apitoken: this.$data.auth.apitoken
                };

                if (!auth.userid || !auth.apitoken) {

                    this.$data.error = 'Ungültige Eingaben!';
                    return false;
                }

                console.log(auth);

                // TODO: try to login and redirect
                return $router.load({url: '/about/'});
            }
        },
        data: function () {
            return {
                title: 'Login',
                auth: {
                    userid: null,
                    apitoken: null
                },
                error: null
            };
        }
    }
</script>