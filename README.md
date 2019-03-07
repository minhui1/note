# note

-------------------



##[纯css实现 switch开关](https://minhui1.github.io/note/aggregate.html)

> 直接看代码，利用了css3兄弟选择器   


### 代码块
``` htmlbars
<label class="m-switch">			
	<input type="checkbox">
	<span></span>		        
</label>
<label class="m-switch">			
	<input type="checkbox" checked="checked">
	<span></span>		        
</label>
```
`注：h1+p 选择紧接在另一个元素后的元素，而且二者有相同的父元素。只会选择第一个相邻的匹配元素。`
```css
.m-switch{display: inline-block; position: relative; cursor: pointer; user-select: none; padding-right: 10px;}
.m-switch input[type="checkbox"]{opacity: 0; position: absolute;}
.m-switch input[type="checkbox"] + span{position: relative; display: inline-block; box-sizing: border-box; width: 40px; height: 24px; background: #fff; box-shadow: inset 0 0 0 0.09375em #ebebeb; border-radius: 30px; transition: all 0.3s cubic-bezier(0.17, 0.67, 0.43, 0.98);}
.m-switch input[type="checkbox"]:checked + span{box-shadow: inset 0 0 0 1.25em #5183C6;}
.m-switch input[type="checkbox"] + span:after{position: absolute; content: ''; width: 22px; height: 22px; border-radius: 50%; top: 50%; -webkit-transform: translateY(-50%); -ms-transform: translateY(-50%); -moz-transform: translateY(-50%); -o-transform: translateY(-50%); transform: translateY(-50%); left: 1px; background: #fff; box-shadow: inset 0 0 0.125em -0.0625em rgba(0, 0, 0, 0.8), 0 0.0625em 0.0625em 0.03125em rgba(0, 0, 0, 0.1), 0 0.1875em 0.0625em 0.03125em rgba(0, 0, 0, 0.15), 0 0.3125em 0.3125em 0 rgba(0, 0, 0, 0.1); transition: all 0.2s linear;}
.m-switch input[type="checkbox"]:checked + span:after{left: 17px;}
```
![Alt text](https://minhui1.github.io/note/images/1551936408037.jpg)



##[纯css实现checkbox的checked样式](https://minhui1.github.io/note/aggregate.html)

> 直接看代码，纯css也能实现checked样式

### 代码块
``` htmlbars
<label><em class="W-checkbox"><input name="" id="cc" type="checkbox" value=""><i></i></em><font>没选中</font></label>
<label><em class="W-checkbox"><input name="" id="cc" type="checkbox" checked="checked" value=""><i></i></em><font>选中</font></label>
<label><em class="W-radio"><input name="" id="cc" type="radio" value=""><i></i></em><font>没选中</font></label>
<label><em class="W-radio"><input name="" id="cc" type="radio" checked="checked" value=""><i></i></em><font>选中</font></label>
```
`注：根据w3school中的说明，‘:checked‘也是一种选择器，用来选择input被checked的元素`

```css
.W-checkbox,
.W-radio{display: inline-block; width: 16px; height: 16px; position: relative; vertical-align: middle;}
.W-checkbox + font,
.W-radio + font{margin-left: 5px; margin-right: 35px; font-size: 12px; color: #333; vertical-align: middle;}
.W-checkbox input[type="checkbox"],
.W-radio input[type="radio"]{width: 16px; height: 16px; opacity: 0;}
.W-checkbox input[type="checkbox"]+i,
.W-radio input[type="radio"]+i{width: 14px; height: 14px; border-radius: 50%; border:1px solid #DDD; background: #fff; position: absolute; top: 0; left: 0;}
.W-checkbox input[type="checkbox"]+i{border-radius: 0;}
.W-checkbox input[type="checkbox"]+i::after,
.W-radio input[type="radio"]+i::after{position: absolute; left: 50%; top: 50%;}
.W-checkbox input[type="checkbox"]+i::after{content: ''; display: inline-block; border: 1px solid #fff; border-top-width: 0; border-right-width: 0; width: 6px; height: 3px; -webkit-transform: rotate(-40deg);-moz-transform: rotate(-40deg); -ms-transform: rotate(-40deg); -o-transform: rotate(-40deg); transform: rotate(-40deg); margin: -3px 0 0 -4px;}
.W-checkbox input[type="checkbox"]:checked+i{background: #5183C6; border-color:transparent;}
.W-checkbox input[type="checkbox"]:checked+i::after{}
.W-radio input[type="radio"]+i::after{content: ''; width: 6px; height: 6px; background: #fff; border-radius: 50%; margin: -3px 0 0 -3px;}
.W-radio input[type="radio"]:checked+i{background: #5183C6; border-color:transparent;}
.W-radio input[type="radio"]:checked+i::after{}
.W-checkbox input[type="checkbox"]+i.check-disable {border: 1px solid rgba(224, 224, 224,.4) !important;}
.W-checkbox input[type="checkbox"]+i.check-disable::after{display: none; cursor: default;}
.W-checkbox input[type="checkbox"]:checked+i.check-disable{background: none;}
```
![Alt text](https://minhui1.github.io/note/images/1551937818968.jpg)


