<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE html>
<html xmlns='http://www.w3.org/1999/xhtml' xmlns:b='http://www.google.com/2005/gml/b' xmlns:data='http://www.google.com/2005/gml/data' xmlns:expr='http://www.google.com/2005/gml/expr'>
<!-- Giới thiệu:
Được mod bởi Vương Việt Anh và convert bởi Hong Lin -->
  <script language='JavaScript'>
    var msg = &quot;🦄  Bấm chuột phải làm gì, copy suộc à? Sub kênh toai rồi lấy suộc cho lẹ hơn không kk 🤞&quot;;

function disableIE() {
        if(document.all) return alert(msg), !1
}

function disableNS(e) {
        if((document.layers || document.getElementById &amp;&amp; !document.all) &amp;&amp; (2 == e.which || 3 == e.which)) return alert(msg), !1
}
document.layers ? (document.captureEvents(Event.MOUSEDOWN), document.onmousedown = disableNS) : (document.onmouseup = disableNS, document.oncontextmenu = disableIE), document.oncontextmenu = new Function(&quot;alert(msg);return false&quot;), shortcut = {
        all_shortcuts: {},
        add: function(m, g, w) {
                var e = {
                        type: &quot;keydown&quot;,
                        propagate: !1,
                        disable_in_input: !1,
                        target: document,
                        keycode: !1
                };
                if(w)
                        for(var t in e) void 0 === w[t] &amp;&amp; (w[t] = e[t]);
                else w = e;
                e = w.target, &quot;string&quot; == typeof w.target &amp;&amp; (e = document.getElementById(w.target)), m = m.toLowerCase(), t = function(e) {
                        var t;
                        if((e = e || window.event, w.disable_in_input) &amp;&amp; (e.target ? t = e.target : e.srcElement &amp;&amp; (t = e.srcElement), 3 == t.nodeType &amp;&amp; (t = t.parentNode), &quot;INPUT&quot; == t.tagName || &quot;TEXTAREA&quot; == t.tagName)) return;
                        e.keyCode ? code = e.keyCode : e.which &amp;&amp; (code = e.which), t = String.fromCharCode(code).toLowerCase(), 188 == code &amp;&amp; (t = &quot;,&quot;), 190 == code &amp;&amp; (t = &quot;.&quot;);
                        var o = m.split(&quot;+&quot;),
                                n = 0,
                                a = {
                                        &quot;`&quot;: &quot;~&quot;,
                                        1: &quot;!&quot;,
                                        2: &quot;@&quot;,
                                        3: &quot;#&quot;,
                                        4: &quot;$&quot;,
                                        5: &quot;%&quot;,
                                        6: &quot;^&quot;,
                                        7: &quot;&amp;&quot;,
                                        8: &quot;*&quot;,
                                        9: &quot;(&quot;,
                                        0: &quot;)&quot;,
                                        &quot;-&quot;: &quot;_&quot;,
                                        &quot;=&quot;: &quot;+&quot;,
                                        &quot;;&quot;: &quot;:&quot;,
                                        &quot;&#39;&quot;: &#39;&quot;&#39;,
                                        &quot;,&quot;: &quot;&lt;&quot;,
                                        &quot;.&quot;: &quot;&gt;&quot;,
                                        &quot;/&quot;: &quot;?&quot;,
                                        &quot;\\&quot;: &quot;|&quot;
                                },
                                c = {
                                        esc: 27,
                                        escape: 27,
                                        tab: 9,
                                        space: 32,
                                        return: 13,
                                        enter: 13,
                                        backspace: 8,
                                        scrolllock: 145,
                                        scroll_lock: 145,
                                        scroll: 145,
                                        capslock: 20,
                                        caps_lock: 20,
                                        caps: 20,
                                        numlock: 144,
                                        num_lock: 144,
                                        num: 144,
                                        pause: 19,
                                        break: 19,
                                        insert: 45,
                                        home: 36,
                                        delete: 46,
                                        end: 35,
                                        pageup: 33,
                                        page_up: 33,
                                        pu: 33,
                                        pagedown: 34,
                                        page_down: 34,
                                        pd: 34,
                                        left: 37,
                                        up: 38,
                                        right: 39,
                                        down: 40,
                                        f1: 112,
                                        f2: 113,
                                        f3: 114,
                                        f4: 115,
                                        f5: 116,
                                        f6: 117,
                                        f7: 118,
                                        f8: 119,
                                        f9: 120,
                                        f10: 121,
                                        f11: 122,
                                        f12: 123
                                },
                                r = !1,
                                s = !1,
                                l = !1,
                                u = !1,
                                d = !1,
                                i = !1,
                                h = !1,
                                f = !1;
                        e.ctrlKey &amp;&amp; (u = !0), e.shiftKey &amp;&amp; (s = !0), e.altKey &amp;&amp; (i = !0), e.metaKey &amp;&amp; (f = !0);
                        for(var p = 0; k = o[p], p &lt; o.length; p++) &quot;ctrl&quot; == k || &quot;control&quot; == k ? (n++, l = !0) : &quot;shift&quot; == k ? (n++, r = !0) : &quot;alt&quot; == k ? (n++, d = !0) : &quot;meta&quot; == k ? (n++, h = !0) : 1 &lt; k.length ? c[k] == code &amp;&amp; n++ : w.keycode ? w.keycode == code &amp;&amp; n++ : t == k ? n++ : a[t] &amp;&amp; e.shiftKey &amp;&amp; ((t = a[t]) == k &amp;&amp; n++);
                        if(n == o.length &amp;&amp; u == l &amp;&amp; s == r &amp;&amp; i == d &amp;&amp; f == h &amp;&amp; (g(e), !w.propagate)) return e.cancelBubble = !0, e.returnValue = !1, e.stopPropagation &amp;&amp; (e.stopPropagation(), e.preventDefault()), !1
                }, this.all_shortcuts[m] = {
                        callback: t,
                        target: e,
                        event: w.type
                }, e.addEventListener ? e.addEventListener(w.type, t, !1) : e.attachEvent ? e.attachEvent(&quot;on&quot; + w.type, t) : e[&quot;on&quot; + w.type] = t
        },
        remove: function(e) {
                e = e.toLowerCase();
                var t = this.all_shortcuts[e];
                if(delete this.all_shortcuts[e], t) {
                        e = t.event;
                        var o = t.target;
                        t = t.callback;
                        o.detachEvent ? o.detachEvent(&quot;on&quot; + e, t) : o.removeEventListener ? o.removeEventListener(e, t, !1) : o[&quot;on&quot; + e] = !1
                }
        }
}, shortcut.add(&quot;Ctrl+U&quot;, function() {
        top.location.href = &quot;https://www.youtube.com/@yutagashi_ths&quot;
}), shortcut.add(&quot;F12&quot;, function() {
        top.location.href = &quot;https://www.youtube.com/@yutagashi_ths&quot;
}), shortcut.add(&quot;Ctrl+Shift+I&quot;, function() {
        top.location.href = &quot;https://www.youtube.com/@yutagashi_ths&quot;
}), shortcut.add(&quot;Ctrl+S&quot;, function() {
        top.location.href = &quot;https://www.youtube.com/@yutagashi_ths&quot;
}), shortcut.add(&quot;Ctrl+Shift+C&quot;, function() {
        top.location.href = &quot;https://www.youtube.com/@yutagashi_ths&quot;
})
</script>
    <head>
        <title>Hong Lin</title>
        <meta charset='UTF-8'/>
        <meta content='width=device-width,initial-scale=1' name='viewport'/>
        <meta content='ie=edge' http-equiv='X-UA-Compatible'/>
        <link href='https://i.imgur.com/lO55gnS.jpeg' rel='icon'/>
        <meta content='Trang chủ của Hong Lin - Welcome to the website.' name='description'/>
        <meta content='Honglin' name='author'/>
        <meta content='Honglin, Hong Lien Se Code, Vuong Viet Anh' name='keywords'/>
        <meta content='width=device-width,initial-scale=1,shrink-to-fit=no' name='viewport'/>
        <link href='https://i.imgur.com/lO55gnS.jpeg' rel='shortcut icon' type='image/x-icon'/>
        <meta content='honglinp5.blogspot.com' property='og:url'/>
        <meta content='https://i.imgur.com/jPv2bcD.png' property='og:image'/>
        <meta content='200' property='og:image:width'/>
        <meta content='200' property='og:image:height'/>
        <meta content='About Me' property='og:image:alt'/>
        <meta content='#00FFFF' name='theme-color'/>
        <meta content='index, follow' name='robots'/>
        <meta content='website' property='og:type'/>
        <link crossorigin='anonymous' href='https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css' integrity='sha384-8S5/LAB9s6rxLvggnUpPA6vfUdF1fQ2wiSs6VgkSO4cQcQ72xQexzxt+V/IZUPZI' rel='stylesheet'/>
        <link href='https://fonts.googleapis.com/css?family=Raleway+Dots' rel='stylesheet' type='text/css'/>
        <link href='https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css' rel='stylesheet' type='text/css'/>
        <script src='https://thglamtesst.000webhostapp.com/api/assets/js/js_index.js'/>
        <link href='https://cdn.jsdelivr.net/npm/boxicons@2.0.7/css/boxicons.min.css' rel='stylesheet'/>
        <b:skin><![CDATA[
        /* Chèn CSS vào đây */
:root{--blue:rgb(0,242,255);--black:rgb(0,0,0);--white:rgb(255,255,255);--red:rgb(255,0,0)}html{font-family:'Segoe UI',Tahoma,Geneva,Verdana,sans-serif}body{background-color:var(--black);display:block;max-height:100vh;max-width:100vw;overflow:hidden;position:relative}.main{width:100vw;color:var(--white);display:flex;flex-direction:column;align-items:center;justify-content:center;position:absolute;top:64px;z-index:50}::selection{background-color:var(--white);color:var(--black)}body.light-mode{background-color:var(--white)}.light-mode::selection{background-color:var(--black);color:var(--blue)}*,body{margin:0;padding:0}.card_information,.infor_content_1{box-shadow:rgba(0,0,0,.3) 0 19px 38px,rgba(0,0,0,.22) 0 15px 12px}:root{--blue:rgb(0,242,255);--trueBlack:rgb(0,0,0);--trueWhite:rgb(255,255,255);--red:rgb(186,42,42);--black:rgb(0,0,0);--white:rgb(255,255,255);--max-witdh:1208px}body{overflow:auto!important;background-color:unset;height:unset}.container{position:fixed!important;top:0;background-image:linear-gradient(0deg,#00000000 1%,#000 99%);backdrop-filter:blur(10px);left:0}.img_avatar,a{position:relative}*{box-sizing:border-box}html{font-family:'Segoe UI',Tahoma,Geneva,Verdana,sans-serif}a{color:unset;text-decoration:none;color:var(--blue)}.navbar{z-index:100}.menu-navbar-right{width:unset!important}.light-mode .container{background-color:var(--white)}.active{display:flex!important}.active_{color:#d86ab7;font-weight:700}::-webkit-scrollbar{width:0}::-webkit-scrollbar:hover{width:0}h4{margin-bottom:0}p{margin-top:0}ul{list-style:none}.main{background-color:var(--trueBlack);top:0;display:block;padding-bottom:30px}.background_img{height:300px;width:100vw;z-index:1}.name_basic,.name_center{height:100px;align-items:center;display:flex}.background_img img{width:100vw;height:100%;object-fit:cover;z-index:1}.name_basic{background-color:#2b2929;z-index:999}.name_center{width:var(--max-witdh);margin:auto;padding:0 20px;justify-content:space-between}.name_left,.view_post{display:flex;align-items:center}.img_avatar{--x:200px;width:var(--x);display:flex;justify-content:center;align-items:center;margin-bottom:30px;margin-right:20px;border-radius:50%;width:150px}.frame_avatar{position:absolute;left:-33px;top:-25px;width:190px;cursor:none}.icon_ghim,.like_icons,.more_options_{cursor:pointer}.status_discord{position:absolute;bottom:35px;right:15px;--x:35px;width:var(--x);height:var(--x);border-radius:50%;background-color:#e100ff;border:5px solid var(--trueWhite)}.true-nick_name{display:flex;flex-direction:column}.true_name{font-size:32px;font-weight:700;color:var(--white);line-height:32px}.more_options ion-icon,.nick_name{font-size:20px}.nick_name{line-height:20px;font-weight:lighter}.weiu{display:flex;justify-content:flex-start;align-items:center}.weiu li{margin-right:10px}.weiu li:nth-last-child(){margin-right:unset}.card_top ul,.code_descript,.main_ely:hover div.tool_ely_active,.more_options{display:flex}.like,.more_options a{padding:8px 10px;border-radius:5px;background-color:#6e6d6d;text-align:center;display:flex;align-items:center}.follow_icon{margin-right:5px}.like{margin-left:10px}.main_about_scroll-child{width:var(--max-witdh);margin:10px auto auto;padding:0 20px 17px;display:flex;flex-direction:column;align-items:center;justify-content:center;background-color:#2b2929;border-radius:10px}.menu_options{width:100%;display:flex;justify-content:space-around;align-items:center;margin:10px 5px;border-bottom:1px solid #939494}.basic_infor,.contr_volumeicon,.like_false,.like_true{display:none}.menu_options li{cursor:pointer;padding:0 10px 10px;border-bottom:2px solid transparent;transition:border-bottom .3s ease-out}.menu_options li.active_,.menu_options li:hover{border-bottom:3px solid #f0d}.like_icons{padding:3px;border-radius:50%;transition:.3s ease-in-out}.card_information,.infor_content_1,.post_item{border-radius:10px}.like_true{color:#fff;transform:scale(1.1);background-color:red}.iuwk_iag{margin:20px}.infor_content_1{position:relative;padding:10px;background-color:#424140;margin:24px}.icon_ghim{position:absolute;top:-30px;left:0;font-size:30px}.icon_ghim_2{left:unset;right:0;top:-25px}.card_information,.card_information_code{width:600px;margin:auto;font-family:Consloas,monospace}.card_information{overflow:hidden;margin:20px auto}.post_infor,.post_item{margin-bottom:20px}.card_top{padding:10px;background-color:#862a2a}.card_top ul li{--xy:23px;width:var(--xy);height:var(--xy);border-radius:50%}.card_top ul li:first-child{background-color:#f30;margin-right:10px}.card_top ul li:nth-child(2){background-color:#ff9100;margin-right:10px}.card_top ul li:nth-child(3){background-color:#04e622}.card_bottom{display:flex;flex-direction:column;align-items:flex-start;padding:18px;background-color:#000}.post_item,div.jhagi_elysia{background-color:#464646;padding:20px}.code_key_value{display:flex;align-items:flex-start;flex-direction:column;margin-left:20px}.code_color-pink{color:#ae00ff}.code_color_yellow{color:#fb0}.posts{width:100%;display:none}div#main_post_scroll{width:var(--max-witdh);margin:auto;padding:20px;display:flex;justify-content:space-evenly}div#items_scroll{width:55%;display:flex;flex-direction:column;justify-content:center}.post_infor,div.infor_post_{align-items:center;display:flex}.hidden_control,.weiurf{background-color:#00f2ff}.post_item:last-child(){margin-bottom:0}.post_infor img{width:64px;border-radius:50%;margin-right:10px;cursor:none}.video_post{max-width:400px;max-height:400px;border-radius:10px}.iuwyj .post_name{font-size:18px;font-weight:700}.iuwyj .post_time{font-size:16px}.tittle_post{font-size:24px;font-weight:700;margin-bottom:10px}.content_post{font-size:14px;margin:10px auto}.post_img{margin:20px auto}.post_img img{border-radius:10px;object-fit:cover;max-height:350px;width:90%;max-width:570px;cursor:none}.hashtag{color:#07f;margin:10px;cursor:pointer;font-weight:700}.post_img video{max-width:100%}div.infor_post_{justify-content:space-around;font-size:24px}.count_views{font-size:16px;margin-left:10px}.source_post{color:#f0f8ff}.source_post ion-icon:hover{color:#000;font-weight:700}div.jhagi_elysia{position:sticky;top:90px;display:flex;align-items:center;flex-direction:column;max-height:680px;max-width:336px;border-radius:10px;width:50%}.jhagi_elysia img{width:100%;border-radius:10px;max-height:500px;transition:opacity .5s ease-in-out;border:3px double #f545ac}.best_quotes{margin:20px auto;font-size:18px;font-weight:700;color:#fff;text-align:center}div.img_banner_elysia{margin-top:20px;height:90vh;width:100%;align-items:center;justify-content:center;display:none}.main_ely,div.tool_ely{display:flex;position:relative}.main_ely{margin:auto;max-width:var(--max-witdh);align-items:center;justify-content:center}img.img_banner{margin:auto;width:90%;border-radius:30px;object-fit:cover}.qiouw{position:fixed;left:-180px;bottom:0;z-index:999;height:54px;transition:color .3s ease-in-out;background-size:100% 100%;background-position:0 0;background-image:linear-gradient(90deg,#a100FFFF 0,#71c4FFFF 100%)}.icon_control,.tool_ely ion-icon{color:#fff;transition:color .3s ease-out}div.tool_ely{width:100%;justify-content:space-evenly;align-items:center;padding:10px;height:100%}.tool_ely ion-icon{font-size:24px;margin:0 10px;padding:5px;border-radius:50%;cursor:pointer}.tool_ely ion-icon:hover{color:#f0f;background-color:#fff;border:1px solid #00b7ff}.icon_control{font-size:30px;border:1px solid #00b7ff;display:none}.weiurf{position:absolute;top:0;right:-50px;width:54px;height:54px;border-top-right-radius:10px;border-bottom-right-radius:10px;display:flex;justify-content:center;align-items:center}.hidden_control{display:none;padding:4px;border-radius:50%}.tranform{transform:translateX(180px)}@media (max-width:1260px){div#main_about_scroll-parent,div.name_basic{padding:10px 20px}.main_about_scroll-child,.name_center{width:100%}}@media (max-width:1024px){.name_basic{height:130px}}@media (max-width:900px){div#items_scroll,div#main_post_scroll{width:100%}div.jhagi_elysia{display:none}}@media (max-width:768px){.background_img{height:200px}.name_basic{height:230px;padding:20px}.name_center{width:100%;height:100%;display:flex;flex-direction:column;justify-content:flex-end;align-items:center;margin:0}.name_left{display:flex;flex-direction:column}.true-nick_name{align-items:center;margin-bottom:20px}.img_avatar{margin-right:0;margin-bottom:10px;--x:130px;width:var(--x)}.frame_avatar{--x:160px;width:var(--x);left:-14px;top:-18px}.status_discord{bottom:15px;--xy:30px;width:var(--xy);height:var(--xy)}.basic_infor,.card_bottom,.card_top{width:100%}.iuwk_iag{width:100%;margin:0}.infor_content_1{width:100%;margin:20px 0 0}.card_information_code{margin:0;width:100%}.card_information{width:unset;font-size:14px}.card_top ul li{--xy:18px}.post_img img,.post_img video{max-width:100%}div#main_post_scroll{padding:0}}@media (max-width:510px){.nick_name{display:block;margin:auto}}@media (max-width:425px){.main_about_scroll-child,.post_item,div#main_about_scroll-parent{padding:10px}.true_name{display:flex;align-items:center;flex-direction:column}.content_post,.iuwyj .post_name,.iuwyj .post_time,.menu_options li{font-size:13px}.post_infor img{width:50px}.count_views,.hashtag,.tittle_post{font-size:14px}}@media (max-width:320px){.card_information_code{font-size:10px}.pronuns,.quotes_nino,.weiu,a.more_options_{font-size:13px}.pronuns{margin:10px auto}}:root{--blue:rgb(0,242,255);--black:rgb(0,0,0);--white:rgb(242,242,242);--red:rgb(255,0,0)}.footer{height:54px;position:fixed;bottom:0;left:50%;transform:translate(-50%,0);z-index:100}.copyright{display:flex;justify-content:center;align-items
