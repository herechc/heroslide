# 简介	
判断上下滑动的插件
#使用
	var slide=new heroSlide()
#详解
	_move: function(e) {
    var that = this;
    if (that.istimer) return;
      var point = hasTouch ? e.touches[0] : e,
      y = point.pageY;
    if (y < that.variableY) {/*判断上划*/
      that.variableY = y;
      console.log("上")
      that.isMove = false;
      that.isdown = false;
    } else if (y > that.variableY) {/*判断下划*/
      that.variableY = y;
      console.log("下");
      that.isMove = true;
    }
    if (that.isMove) {/*判断上下划几次触发（根据that.isMove）*/
      if (that.isdown) return false;
      that.moveIndex++;
      console.log(that.moveIndex)
      that.isdown = true;
      that.isMove = false;
    }
  },
	
