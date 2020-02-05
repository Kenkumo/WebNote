
# HTML

# HTML标签

## 排版标签

### 标题标签

### 段落标签

### 水平线标签

### 换行标签

### div和span标签

## 文本格式化标签

## 图像标签

## 链接标签

### 锚点定位

### base标签

## 特殊字符标签

## 列表标签

### 无序列表

### 有序列表

### 自定义列表

## 表格

### 表格属性

### 表头标签

### 合并单元格

## 表单标签

### input控件

### label标签

### textarea控件（文本域）

### 下拉菜单

### 表单域

# HTML5新标签与特性

## 常用新标签

- 定义文档的页眉：
- 定义导航链接的部分：
- 定义文档或节的页脚：
- 标签规定独立的自包含内容：
- 定义文档中的节：
- 定义其所处内容之外的内容：
- 选项列表：
- 组合表单中相关元素：

## 常用新属性

| 属性 | 用法                     | 含义                            |
| ---- | ------------------------ | ------------------------------- |
|      | `<input type="text"  />` | 占位符                          |
|      | `<input type="text"  />` | 页面加载时input元素自动获得焦点 |
|      | `<input type="text"  />` | 多文件上传                      |
|      | `<input type="text"  />` | 表单启用自动完成功能            |
|      | `<input type="text"  />` | 必填项                          |
|      | `<input type="text"  />` | 设置激活元素的快捷键            |

## 新增type属性值

| 类型     | 使用示例                  | 含义                 |
| -------- | ------------------------- | -------------------- |
| email    | `<input type="email">`    | 输入邮箱格式         |
| tel      | `<input type="tel">`      | 输入手机号码格式     |
| url      | `<input type="url">`      | 输入url格式          |
| number   | `<input type="number">`   | 输入数字格式         |
| search   | `<input type="search">`   | 搜索框（体现语义化） |
| range    | `<input type="range">`    | 自由拖动滑块         |
| time     | `<input type="time">`     |                      |
| date     | `<input type="date">`     |                      |
| datetime | `<input type="datetime">` |                      |
| month    | `<input type="month">`    |                      |
| week     | `<input type="week">`     |                      |

## 综合案例

```html
<form action="">
  <fieldset>
    <legend>学生档案</legend>
    <label for="userName">姓名:</label>
    <input type="text" name="userName" id="userName" placeholder="请输入用户名"> <br>
    <label for="userPhone">手机号码:</label>
    <input type="tel" name="userPhone" id="userPhone" pattern="^1\d{10}$"><br>
    <label for="email">邮箱地址:</label>
    <input type="email" required name="email" id="email"><br>
    <label for="collage">所属学院:</label>
    <input type="text" name="collage" id="collage" list="cList" placeholder="请选择"><br>
    <datalist id="cList">
      <option value="前端与移动开发学院"></option>
      <option value="java学院"></option>
      <option value="c++学院"></option>
    </datalist><br>
    <label for="score">入学成绩:</label>
    <input type="number" max="100" min="0" value="0" id="score"><br>
    <label for="level">基础水平:</label>
    <meter id="level" max="100" min="0" low="59" high="90"></meter><br>
    <label for="inTime">入学日期:</label>
    <input type="date" id="inTime" name="inTime"><br>
    <label for="leaveTime">毕业日期:</label>
    <input type="date" id="leaveTime" name="leaveTime"><br>
    <input type="submit">
  </fieldset>
</form>
```

## 多媒体标签

### 多媒体embed

### 多媒体 audio

### 多媒体 video