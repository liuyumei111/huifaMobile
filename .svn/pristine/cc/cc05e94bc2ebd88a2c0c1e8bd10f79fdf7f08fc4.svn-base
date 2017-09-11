(function ($) {

	//选项卡插件
	$.fn.newTabs = function tab(options) {
		var id = $(this); //这里的this就是当前调用此方法的对象  $("#tabs")
		var items = id.find(".tabCont>div").eq(options.index).show().end();
		var $prev;
		id.find(".tabs>div").eq(options.index).addClass(options.activeClass).end().on('tap', function () {
			var $this = $(this);
			if ($prev && $prev.get(0) == $this.get(0)) return;
			$prev = $this;
			$this.addClass(options.activeClass).siblings().removeClass(options.activeClass);
			var index = $this.index();
			items.hide().eq(index).fadeIn(500);

			options.currIndexCallBack && options.currIndexCallBack(index);
		})
	}

	//tabs固定顶栏
	$.fn.scrollFixed = function (className) {
		var _this = $(this),
		tabsOffsetTop = Math.floor(_this.offset().top),
		flag = true,
		$body = $("body");
		$(document).on("scroll", function () {
			if ($body.scrollTop() > tabsOffsetTop) {
				flag && _this.addClass(className);
				flag = false;
			} else {
				flag || _this.removeClass(className);
				flag = true;
			}
		})
	}



	$.fn.accordion = function (options) {
		/// <summary>
		/// 手风琴菜单插件
		/// </summary>
		/// <param name="options" type="Object">配置参数</param>
		/// <returns type="jQuery"></returns>
		/*演示*/
		//$(".accordion").accordion({
		//	flag: true,//规定是否只展开单项功能,默认为false 可以展开多项
		//	activeClass: "title-active" //规定当前展开项的class样式
		//});
		options = options || {};
		var $this = $(this), $prev, activeClass = options.activeClass || null;
		var handlerTap = function () {
			if ($prev && $(this).get(0) !== $prev.get(0) && options.flag) {
				$prev = $prev.removeClass(activeClass).next().slideUp().end();
			}
			//处理activeClass样式
			if (activeClass && typeof activeClass === "string") {
				if ($(this).hasClass(activeClass)) $(this).removeClass(activeClass);
				else $(this).addClass(activeClass);
			}
			$prev = $(this).next().slideToggle(300).end();
		}
		$this.find(".menu-nav-list>li>span").on("tap", handlerTap);
		return $this;
	}



	var Tool = function () {
		var tool = {
			setScrollTop: function (scrollTop) {
				/// <summary>
				/// 重置滚动条到指定位置
				/// </summary>
				/// <param name="scrollTop" type="type"></param>
				if (typeof scrollTop !== "number") return false;
				var $body = $("body");
				$body.scrollTop() > scrollTop && $body.scrollTop(scrollTop);
			}
		}


		return tool;
	}




	$.extend(Tool());

})(jQuery)