


-------------------



##纯css实现 switch开关

> 直接看代码，利用了css3兄弟选择器    —— [dome](https://minhui1.github.io/note/switch.html)



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
```css
.m-switch{display: inline-block; position: relative; cursor: pointer; user-select: none; padding-right: 10px;}
.m-switch input[type="checkbox"]{opacity: 0; position: absolute;}
.m-switch input[type="checkbox"] + span{position: relative; display: inline-block; box-sizing: border-box; width: 40px; height: 24px; background: #fff; box-shadow: inset 0 0 0 0.09375em #ebebeb; border-radius: 30px; transition: all 0.3s cubic-bezier(0.17, 0.67, 0.43, 0.98);}
.m-switch input[type="checkbox"]:checked + span{box-shadow: inset 0 0 0 1.25em #5183C6;}
.m-switch input[type="checkbox"] + span:after{position: absolute; content: ''; width: 22px; height: 22px; border-radius: 50%; top: 50%; -webkit-transform: translateY(-50%); -ms-transform: translateY(-50%); -moz-transform: translateY(-50%); -o-transform: translateY(-50%); transform: translateY(-50%); left: 1px; background: #fff; box-shadow: inset 0 0 0.125em -0.0625em rgba(0, 0, 0, 0.8), 0 0.0625em 0.0625em 0.03125em rgba(0, 0, 0, 0.1), 0 0.1875em 0.0625em 0.03125em rgba(0, 0, 0, 0.15), 0 0.3125em 0.3125em 0 rgba(0, 0, 0, 0.1); transition: all 0.2s linear;}
.m-switch input[type="checkbox"]:checked + span:after{left: 17px;}
```


