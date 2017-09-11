$(function () {

        //初始化Banner 轮播图
        var banner = new Swiper('.swiper-banner', {
                loop: true,
                pagination: '.swiper-pagination',
                paginationClickable: true,
                spaceBetween: 0,
                centeredSlides: true,
                autoplay: 2500,
                autoplayDisableOnInteraction: false
        });



        //初始化tabs选项卡
        $("#tabs").newTabs({
                activeClass: "tab-active",
                index: 0,
                currIndexCallBack: function (index) {
                        //点击切换之后回到顶部
                        $.setScrollTop($(".main").offset().top);

                        if (index === 2) {
                                //初始化案例集swiper效果
                                var swiper = new Swiper('.swiper-cases', {
                                        initialSlide: Math.ceil(5 / 2) - 1,
                                        effect: 'coverflow',
                                        grabCursor: true,
                                        centeredSlides: true,
                                        slidesPerView: 'auto',
                                        //loop: true,
                                        coverflow: {
                                                rotate: 0,
                                                stretch: -40,
                                                depth: 200,
                                                modifier: 1,
                                                slideShadows: true
                                        },
                                        //onTransitionEnd: this.onTransitionEnd.bind(this)
                                });
                                swiper = null;
                        }
                }
        });


        //设置悬浮tabs
        $(".tabs").scrollFixed("tabsF");

        //初始化手风琴菜单部分
        $("#accordion").accordion({
                flag: true,//规定是否只展开单项功能,默认为false 可以展开多项
                activeClass: "title-active" //规定当前展开项的class样式
        });

        var menuNav = $(".menu-nav");
        //点击X按钮关闭菜单
        menuNav.find(".menu-header .close").on("tap", function () {
                menuNav.slideUp();
        });
        //点击导航menu按钮打开关闭菜单
        $(".header .menu").on("tap", function () {
                menuNav.slideToggle();
        });

})