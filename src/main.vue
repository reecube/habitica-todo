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
                    <f7-nav-center sliding>Login</f7-nav-center>
                </f7-navbar>

                <!-- Pages -->
                <f7-pages>
                    <f7-page>
                        <f7-list form>
                            <f7-list-item>
                                <f7-label>Benutzer-ID</f7-label>
                                <f7-input name="user-id" placeholder="Benutzer-ID" type="text"></f7-input>
                            </f7-list-item>
                            <f7-list-item>
                                <f7-label>API-Token</f7-label>
                                <f7-input name="api-token" placeholder="API-Token" type="password"></f7-input>
                            </f7-list-item>
                        </f7-list>
                        <f7-list>
                            <f7-list-button @click="login" title="Einloggen"></f7-list-button>
                        </f7-list>
                    </f7-page>
                </f7-pages>
            </f7-view>
        </f7-views>
    </div>
</template>

<script>
    export default {}
</script>