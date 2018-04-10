# wepy-canlendar
---
一款微信小程序的日历组件 支持左右翻页,picker.

## Screenshots



<img src="http://or9d9eqg0.bkt.clouddn.com/calendar2" width="288"/>

<img src="http://or9d9eqg0.bkt.clouddn.com/calendar3.png" width="288"/>

<img src="http://or9d9eqg0.bkt.clouddn.com/calendar.gif" width="288"/>


## Usage
### 首先记得把asset/icons下的2个小图标放到自己的资源文件里哦
### 项目依赖moment
### cnpm install moment --save

```js
import calendar from '../components/calendar

<calendar :visible.sync="calendarVisible"  :value.sync="time" @hanleConfirm.user="hanleConfirm" color="#05c8d3"></calendar>
  data = {
    calendarVisible: false,
    time: '2018-04-11'
  }
  components = {
    calendar
  }
  methods = {
    showcalendar () {
      this.calendarVisible = true
    },
    hanleConfirm (e) {
      console.log(e)// 导出数据
    }
  }


```
最后导出的数据很友好:
```json
// 导出一个object
{
    day:27,
    formatDay:'2018-05-27',
    month:5,
    weekCh:'周日',
    year: 2018
}

```

## API

### wepy-calendar props

<table class="table table-bordered table-striped">
    <thead>
    <tr>
        <th style="width: 80px;">name</th>
        <th style="width: 50px;">type</th>
        <th style="width: 30px;">default</th>
        <th>description</th>
    </tr>
    </thead>
    <tbody>
        <tr>
          <td>visible</td>
          <td>Boolean</td>
          <td>false</td>
          <td>控制dialog的显示</td>
        </tr>
        <tr>
          <td>value</td>
          <td>String(YYYY-MM-DD)</td>
          <td>moment().format('YYYY-MM-DD')</td>
          <td>日历初始值</td>
        </tr>
        <tr>
          <td>hanleConfirm.user</td>
          <td>自定义事件</td>
          <td>必填</td>
          <td>点击确定按钮触发的钩子</td>
        </tr>
        <tr>
          <td>color</td>
          <td>rgb rgba等(css里的颜色值都可用)</td>
          <td>black</td>
          <td>日历主色</td>
        </tr>

    </tbody>
</table>



## License

wepy-calendar is released under the MIT license.
