# handelbars helpers的书写
## 控制列表的输出数量：
### js中如下书写：

``` js
Handlebars.registerHelper('each_limit_output', function(ary, max, options) {
        if(!ary || ary.length == 0)
            return options.inverse(this);
        var result = [ ];
        for(var i = 0; i < max && i < ary.length; ++i)
            result.push(options.fn(ary[i]));
        return result.join('');
    });
``` js
### html中如下使用：
``` html
{{# each_limit_output list 6}}
			<li class="big-li mb-30">
				<a href="/credit/detail?id={{id}}">
					<img class="fl" src="{{icon}}" alt="{{companyName}}">
					<div class="fl big-desc">
						<h2 title="{{listAdvantage}}">{{limit listAdvantage 14}}</h2>
						<p title="月管理费:{{monthFeeRate}}%">
							月管理费: <span class="bold">{{monthFeeRate}}%</span>
						</p>
						<p title="总费用:{{totalFee}}万元">
							总费用: <span class="bold">{{totalFee}}万元</span>
						</p>
						<p title="{{listAdvantage}}">
							{{limit listAdvantage 14}}
						</p>
					</div>
				</a>
			</li>
		{{/ each_output }}
``` html
