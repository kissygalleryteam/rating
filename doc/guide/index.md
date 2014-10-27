## 综述

starrating是简单易用的星级打分组件。

作者：乔花、剑平å

## 快速使用

### 初始化组件

html结构

    <div id="J_Rating" class="rating-bd s-demo">
        <div class="shop-rating">
            <span class="title">设计美观:</span>
            <ul class="rating-level">
                <li><a href="#" data-star-value="1" class="one-star">1</a></li>
                <li><a href="#" data-star-value="2" class="two-stars">2</a></li>
                <li><a href="#" data-star-value="3" class="three-stars">3</a></li>
                <li><a href="#" data-star-value="4" class="four-stars">4</a></li>
                <li><a href="#" data-star-value="5" class="five-stars">5</a></li>
            </ul>
            <span class="result"></span>
            <input type="hidden" size="2" value="" name="dsr1" />
        </div>
        <div class="rating-pop-tip" style="display: none;"></div>
    </div>

javascript代码

    KISSY.use('kg/rating/2.0.0/index,kg/rating/2.0.0/index.css', function (S, Rating) {
        var a = new Rating({
            container: '#J_Rating',
            reason: [['太丑了', '不好看', '一般般', '很漂亮', '哇!非常漂亮'],
                ['太难维护了', '不好维护', '一般般', '维护很简单', '维护超级容易'],
                ['太慢了', '有点小慢', '一般般', '挺快的', '超级快!']],
            level: ['非常不满意','很不满意','一般','很满意','非常满意']
        });
        a.on('rating', function(ev) {
            S.log('给第' + (ev.idx+1) + '项打分为' + ev.score);
        });
    })


