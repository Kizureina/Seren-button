<template>
    <div id="app">
        <Modal></Modal>
        <nav class="navbar navbar-default navbar-fixed-top">
            <div class="container-fluid">
                <div class="navbar-header">
                    <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-navbar-collapse" aria-expanded="false">
                        <span class="sr-only">{{ $t("action.toggleNavbar") }}</span>
                        <span class="icon-bar"></span>
                        <span class="icon-bar"></span>
                        <span class="icon-bar"></span>
                    </button>
                    <router-link class="navbar-brand" to="/">{{ $t("info.title") }}</router-link>
                </div>
                
                <div class="collapse navbar-collapse" id="bs-navbar-collapse">  
                    <ul class="nav navbar-nav">
                        <li><a href="https://space.bilibili.com/1437582453" target="_blank"><img src="resources/bilibili_social_icon.png" height="18"/></a></li>
                        <li><a href="https://twitter.com/AzumaSeren" target="_blank"><img src="resources/Twitter_Social_Icon_Circle_Color.png" height="18"/></a></li>
                        <li><a href="https://www.youtube.com/c/%E6%9D%B1%E9%9B%AA%E8%93%AESerenAzuma" target="_blank"><img src="resources/youtube_social_icon_red.png" height="18"/></a></li>
                    </ul>
                    <ul class="nav navbar-nav navbar-right">
                        <li class="dropdown">
                            <a href="javascript:;" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">{{$t("lang." + currentLang)}} <span class="caret"></span></a>
                            <ul class="dropdown-menu">
                                <li><a href="javascript:;" @click="chlang('zh-CN')">{{$t("lang.zh-CN")}}</a></li>
                                <!--<li><a href="javascript:;" @click="chlang('en-US')">{{$t("lang.en-US")}}</a></li>-->
                                <li><a href="javascript:;" @click="chlang('ja-JP')">{{$t("lang.ja-JP")}}</a></li>
                            </ul>
                        </li>
                    </ul>
                </div>

            </div>
        </nav>
        <div class="container-fluid main-content">
            <router-view></router-view>
        </div>
        <footer class="footer">
            <div class="container-fluid footer-content">
                <div class="text-center"><a href="https://github.com/A1exMinatoooo/rina-button" target="_blank">{{$t("info.toGithub")}} <img src="https://img.shields.io/github/stars/A1exMinatoooo/rina-button.svg?style=social" class="github-stars-icon"/></a></div>
                <div class="text-center">{{$t("info.notOfficial")}}</div>
                <div class="text-center">{{$t("info.audioStaff")}}</div>
                <div class="text-center">Made with SerenBot</div>
                <div class="text-center"><span style="color: rgba(0, 0, 0, 0.1)">Powered By Meowsound Idols</span></div>
            </div>
        </footer>
    </div>
</template>

<style lang="scss">
@import "../node_modules/bootstrap/dist/css/bootstrap.css";
body{
    padding-top: 60px;
    background-color:#9e97ff;
    background-image: url();
}
.main-content{
    min-height: 100vh;
}
.footer {
    width: 100%;
    height: auto;
    font-size: 75%;
    background-color: #9e97ff;
}
.footer-content {
    padding-top: 10px;
    padding-bottom: 10px;
    color: rgb(29, 39, 225);
}
.text-right{
    text-align: right;
}
.github-stars-icon {
    width: 4%;
}
</style>

<script>
import Vue from 'vue'
import Component from 'vue-class-component'
import Modal from './components/modal.vue'
//import fetchpost from './util/fetchpost'

@Component({
    components:{
        Modal
    }
})
class App extends Vue {
    get currentLang(){
        return this.$i18n.locale;
    }
    created(){
        // eslint-disable-next-line 
        console.log("Produced by MoewSound Idols");
        this.$i18n.locale = localStorage.getItem("lang") || this.$i18n.locale;
    }
    chlang(v){
        this.$i18n.locale = v;
        localStorage.setItem("lang", v);
    }
}

export default App;
</script>

