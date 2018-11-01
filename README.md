利用FirebaseUI for Android 建立註冊登入功能
https://github.com/firebase/FirebaseUI-Android/blob/master/auth/README.md

build.gradle(Moudle:app)

把en改成zh_TW 模擬器改成繁體中文 就能讓Auth-UI變成中文介面

    defaultConfig {
       resConfigs "en" // And any other languages you support
    }

建立Email登入與Google帳戶登入


    startActivityForResult(AuthUI.getInstance().createSignInIntentBuilder()
                    .setIsSmartLockEnabled(false)
                    .setAvailableProviders(Arrays.asList(
                            new AuthUI.IdpConfig.EmailBuilder().build(),
                            new AuthUI.IdpConfig.GoogleBuilder().build()
                    )).build(),RC_SIGN_IN);
