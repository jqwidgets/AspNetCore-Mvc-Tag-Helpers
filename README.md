# ASP .NET Core MVC Tag Helpers

## What is a ASP .NET Core MVC Tag Helper?

Tag Helper enables server-side code to participate in creating and rendering HTML elements in Razor files.

## ASP .NET Core MVC Demos

[ASP .NET Core MVC Tag Helpers Demos page](http://www.jqwidgets.com/jquery-widgets-demo/demos/asp.net-core-mvc-tag-helpers/index.htm).

## What Tag Helpers provide?

In general, HTML-friendly experience.
Razor markup using Tag Helpers looks like standard HTML.
Front-end designers familiar with HTML/CSS/JavaScript can edit
Razor without learning C# Razor syntax. ASP .NET MVC Core
Tag Helpers make you more productive and able to produce more
robust, reliable, and maintainable code using information only
available on the server. With ASP .NET Tag Helpers, you also get
a rich IntelliSense environment for creating HTML and Razor markup.

## Setup

### 1. Create a new ASP .NET Core Web Application
![alt text](http://aspcore.jqwidgets.com/bootstrap/tag-helpers/images/aspnetcore-net-project.png "Tag Helpers 1")

![alt text](http://aspcore.jqwidgets.com/bootstrap/tag-helpers/images/aspnetcore-webapplication.png "Tag Helpers 2")

### 2. Reference the Tag Helpers

Install the Tag Helper's Nuget package from https://www.nuget.org/packages/jQWidgets.AspNetCore.Mvc.TagHelpers/1.0.0.
### 3. Update _ViewImports.cshtml

```
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers
@addTagHelper *, jQWidgets.AspNetCore.Mvc.TagHelpers
@inject Microsoft.ApplicationInsights.Extensibility.TelemetryConfiguration TelemetryConfiguration
```

### 4. Build the Solution

Click Build in the top menu bar of Visual Studio, then click Build Solution to Build the solution

### 5. Add a Tag Helper to a Page

We can now add a Tag Helper to one of the views (pages).
For example, we will add the Tag Helper to Views\Home\About.cshtml.
While typing, IntelliSense suggest the existing Tag Helpers:

```html
@model IEnumerable<jQWidgets.AspNet.Core.Models.Employee>
@{
    ViewData["Title"] = "ASP .NET MVC Grid Example";
}
<script src="~/jqwidgets/jqxbuttons.js"></script>
<script src="~/jqwidgets/jqxscrollbar.js"></script>
<script src="~/jqwidgets/jqxgrid.js"></script>
<script src="~/jqwidgets/jqxgrid.edit.js"></script>
<script src="~/jqwidgets/jqxgrid.columns-resize.js"></script>
<script src="~/jqwidgets/jqxgrid.filter.js"></script>
<script src="~/jqwidgets/jqxgrid.selection.js"></script>
<script src="~/jqwidgets/jqxgrid.sort.js"></script>
<script src="~/jqwidgets/jqxgrid.pager.js"></script>
<script src="~/jqwidgets/jqxgrid.aggregates.js"></script>
<script src="~/jqwidgets/jqxgrid.grouping.js"></script>
<script src="~/jqwidgets/jqxmenu.js"></script>
<script src="~/jqwidgets/jqxlistbox.js"></script>
<script src="~/jqwidgets/jqxdropdownlist.js"></script>

@model IEnumerable<jQWidgets.AspNet.Core.Models.Employee>

@{
    ViewData["Title"] = "ASP .NET MVC Grid Example";
}

<jqx-grid theme="@ViewData["Theme"]" sortable="true" filterable="true" auto-height="true" width="850" source="Model"> 
    <jqx-grid-columns>
        <jqx-grid-column column-group="name" datafield="FirstName" width="100" text="First Name"></jqx-grid-column>
        <jqx-grid-column column-group="name" datafield="LastName" width="100" text="Last Name"></jqx-grid-column>
        <jqx-grid-column datafield="Title" width="150"></jqx-grid-column>
        <jqx-grid-column datafield="Address" width="200"></jqx-grid-column> 
        <jqx-grid-column datafield="City" width="150"></jqx-grid-column>
        <jqx-grid-column datafield="Country"></jqx-grid-column>
  </jqx-grid-columns>
    <jqx-grid-column-groups>
        <jqx-grid-column-group name="name" text="Name"></jqx-grid-column-group>
    </jqx-grid-column-groups>
</jqx-grid>


```

## Bootstrap UI ASP.NET Core Tag Helpers

For those of you who use Twitter Bootstrap, we have yet another
good set of Tag Helpers. We developed more than two dozen Tag Helpers
to help you use Bootstrap with the new ASP.NET MVC Core.
You can find more about the project, see a live demo and download
the library from our
[Bootstrap Tag Helpers page](http://aspcore.jqwidgets.com/bootstrap).

## Tag Helpers

### Grid

The ```jqx-grid``` tag helper allows you to easily append and display a Grid to your web page and data bound to your web server's data source.

```html
<jqx-grid theme="@ViewData["Theme"]" sortable="true" filterable="true" auto-height="true" width="850" source="Model"> 
    <jqx-grid-columns>
        <jqx-grid-column column-group="name" datafield="FirstName" width="100" text="First Name"></jqx-grid-column>
        <jqx-grid-column column-group="name" datafield="LastName" width="100" text="Last Name"></jqx-grid-column>
        <jqx-grid-column datafield="Title" width="150"></jqx-grid-column>
        <jqx-grid-column datafield="Address" width="200"></jqx-grid-column> 
        <jqx-grid-column datafield="City" width="150"></jqx-grid-column>
        <jqx-grid-column datafield="Country"></jqx-grid-column>
  </jqx-grid-columns>
    <jqx-grid-column-groups>
        <jqx-grid-column-group name="name" text="Name"></jqx-grid-column-group>
    </jqx-grid-column-groups>
</jqx-grid>
```

The Grid tag helper shares the same API members as the Javascript Grid widget i.e all properties, methods and events can be used. Additional properties for the ```jqx-grid``` tag helper are:

```
create - {{String}} which determines the URL called when a Grid row is added.
datafield-for - {{ModelExpression}} used for model binding and determines the column's bound member.
delete - {{String}} which determines the URL called when a Grid row is deleted.
edit - {{String}} which determines the URL called when the Grid is edited.
instance - {{String}} which determines the javascript member within the Script tag which refers to the Grid's instance. This member is useful when you want to dynamically invoke API members of the Javascript component.
server-processing - {{Boolean}} which determines whether server processing is enabled.
source-id - {{String}} which determines the data source's ID member.
source-id-for - {{ModelExpression}} used for model binding and determines the data source's ID member.
source-root - {{String}} which determines the data source's Root member.
source-total-records - {{Integer}} which determines the data source's TotalRecords member.
source-url - {{String}} which determines the data source's URL.
source-model - {{Model}} which determines the data source's Model.
```

```jqx-grid-columns``` tag helper should be defined within the ```jqx-grid``` tag helper and defines the Grid columns collection.<br />
```jqx-grid-column``` tag helper should be defined within the ```jqx-grid-columns``` tag helper and defines a Grid column.<br />
```jqx-grid-column-groups``` tag helper should be defined within the ```jqx-grid``` tag helper and defines the Grid columns hierarchy.<br /> 
```jqx-grid-column-group``` tag helper should be defined within the ```jqx-grid-column-groups``` tag helper and defines a Grid column group.<br />

### Bar Gauge

The ```jqx-bar-gauge``` tag helper adds a Bar Gauge component to a web page.

```html
<script src="~/jqwidgets/jqxbargauge.js"></script>

@{
    ViewData["Title"] = "ASP .NET MVC Bar Gauge Example";
    List<string> ranges = new List<string>()
    {
        "{ start-value: 0, end-value: 200, color: \"#000000\", opacity: 0.5 }",
        "{ start-value: 200, end-value: 250, color: \"#000000\", opacity: 0.3 }",
        "{ start-value: 250, end-value: 300, color: \"#000000\", opacity: 0.1 }"
    };
    List<double> barGaugeValues = new List<double>()
    {
        102, 115, 130, 137
    };
}
<div class="example-description">ASP .NET MVC BarGauge Example</div><br />
<jqx-bar-gauge colorScheme="scheme02" ranges="ranges" values="barGaugeValues" width="600" height="600" max="150"></jqx-bar-gauge>```

### Bullet Chart

The ```jqx-bullet-chart``` tag helper adds a Bullet Chart component to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@{
    ViewData["Title"] = "ASP .NET MVC Bullet Chart Example";
    BulletChartDataObject pointer = new BulletChartDataObject()
    {
        Value = 270,
        Label = "Revenue 2016 YTD",
        Size = "25%",
        Color = "Black"
    };
    BulletChartDataObject target = new BulletChartDataObject()
    {
        Value = 260,
        Label = "Revenue 2015 YTD",
        Size = "4",
        Color = "Black"
    };
    BulletChartDataObject ticks = new BulletChartDataObject()
    {
        Position = "both",
        Interval = 50,
        Size = "10"
    };
    List<BulletChartRange> ranges = new List<BulletChartRange>()
    {
        new BulletChartRange()
        {
            StartValue = 0, EndValue = 200, Color = "#000", Opacity = 0.5
        },
        new BulletChartRange()
        {
            StartValue = 200, EndValue = 250, Color = "#000", Opacity = 0.3
        },
        new BulletChartRange()
        {
            StartValue = 250, EndValue = 300, Color = "#000", Opacity = 0.1
        }
    };
}
<label>ASP .NET MVC Core Bullet Chart Tag Helper Example</label><br/><br/>
<jqx-bullet-chart labels-format="c" width="500" height="80" bar-size="40%" pointer="pointer" ticks="ticks" ranges="ranges" target="target"  title="Revenue 2016 YTD" description="(U.S. $ in thousands)" ></jqx-bullet-chart>
```

### Button

The ```jqx-button``` tag helper adds a Button component to a web page.
```jqx-repeat-button``` add a Repeat Button and ```jqx-toggle-button``` adds a toggle button
to the web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC Button, ToggleButton and RepeatButton Example";
}
<label>ASP .NET MVC Button, ToggleButton and RepeatButton Example</label><br/><br/>
<jqx-button theme="@ViewData["Theme"]" on-click="@Url.Action("Increment", "TagHelpers")">Button</jqx-button>
<jqx-toggle-button style="margin-left:20px;" theme="@ViewData["Theme"]">Toggle Button</jqx-toggle-button>
<jqx-repeat-button style="margin-left:20px;" on-click="@Url.Action("Increment", "TagHelpers")" theme="@ViewData["Theme"]">Repeat Button</jqx-repeat-button>
```

### Button Group

The ```jqx-button-group``` tag helper adds a Button Group Chart component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC ButtonGroup Example";
}
<label>ASP .NET Core MVC Button Group Tag Helper Example</label><br/><br/>
Default Mode<br/>
<jqx-button-group theme="@ViewData["Theme"]" id='jqxWidget'>
    <button style="padding:4px 16px;">
        Left
    </button>
    <button style="padding:4px 16px;">
        Center
    </button>
    <button style="padding:4px 16px;">
        Right
    </button>
</jqx-button-group>
Radio Mode<br/>
<jqx-button-group id="buttongroup2" theme="@ViewData["Theme"]" mode="radio">
    <button style="padding:4px 16px;">
        Left
    </button>
    <button style="padding:4px 16px;">
        Center
    </button>
    <button style="padding:4px 16px;">
        Right
    </button>
</jqx-button-group>
CheckBox Mode<br/>
<jqx-button-group id="buttongroup3" theme="@ViewData["Theme"]" mode="checkbox">
    <button style="padding:4px 16px;">
        Left
    </button>
    <button style="padding:4px 16px;">
        Center
    </button>
    <button style="padding:4px 16px;">
        Right
    </button>
</jqx-button-group>
```

### Calendar

The ```jqx-calendar``` tag helper adds a Calendar component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC Calendar Example";
}
<label>ASP .NET Core MVC Calendar Tag Helper Example</label><br/><br/>
<jqx-calendar theme="@ViewData["Theme"]" width="200" height="200" ></jqx-calendar>
```

### Chart

The ```jqx-chart``` tag helper adds a Chart component to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers;
@model IEnumerable<jQWidgets.AspNet.Core.Models.BrowserShare>
@{
    ViewData["Title"] = "ASP .NET MVC Pie Chart Example";
    Padding padding = new Padding() { Left = 5, Top = 5, Right = 5, Bottom = 5 };
    Padding titlePadding = new Padding() { Left = 0, Top = 0, Right = 0, Bottom = 10 };
    Rectangle legendPosition = new Rectangle() { Left = 520, Top = 140, Width = 100, Height = 100 };
    FormatSettings formatSettings = new FormatSettings() { Sufix = "%", DecimalPlaces = 1 };
}
<label>ASP .NET Core MVC Chart Tag Helper Example</label><br/><br/>
<jqx-chart style="width: 850px; height: 500px;" color-scheme="scheme02" padding="padding" title-padding="titlePadding" title="Desktop browsers share" description="(source: wikipedia.org)" show-legend="false" legend-position="legendPosition" source="Model">
    <jqx-chart-series-groups>
         <jqx-chart-serie-group show-labels="true" type=@SerieType.Pie>
                <jqx-chart-series>
                    <jqx-chart-serie datafield="Share" display-text="Browser" label-radius="120" initial-angle="15" radius="170" center-offset="0" format-settings="formatSettings">
                   </jqx-chart-serie>
                </jqx-chart-series>
         </jqx-chart-serie-group>
    </jqx-chart-series-groups>
</jqx-chart>
```

```jqx-chart-series-groups``` tag helper should be defined within the ```jqx-chart``` tag helper and
defines the Chart series groups collection. ```jqx-chart-serie-group``` tag helper should be
defined within the ```jqx-chart-series-groups``` tag helper and defines a Chart serie group.<br />
```jqx-chart-series``` tag helper should be defined within the ```jqx-chart-serie-group``` tag helper
and defines the Chart series collection. <br />
```jqx-chart-serie``` tag helper should be defined within the ```jqx-chart-series``` tag helper and defines a Chart serie. <br />
The ```for``` and ```radiusFor``` members can be used for model binding. <br />
```jqx-chart-x-axis``` tag helper should be defined within the ```jqx-chart``` tag helper and defines the Chart's X Axis. 
The for member can be used for model binding. <br />
```jqx-chart-value-axis``` tag helper should be defined within the ```jqx-chart``` tag helper and defines the Chart's Value Axis. <br />
```jqx-chart-title``` tag helper should be defined within the ```jqx-chart-value-axis``` tag helper and defines the Chart's Title. <br />
```jqx-chart-labels``` tag helper should be defined within the ```jqx-chart-value-axis``` tag helper and defines the Chart's Labels.<br />
```jqx-chart-range-selector``` tag helper should be defined within the ```jqx-chart``` tag helper and defines the Chart's Range selector.

```html
@model IEnumerable<jQWidgets.AspNet.Core.Models.ChartSalesDataItem>
@using jQWidgets.AspNetCore.Mvc.TagHelpers;
@{
    ViewData["Title"] = "ASP .NET MVC Bubble Chart Example";
    var item = Model.FirstOrDefault();
    Padding padding = new Padding() { Left = 5, Top = 5, Right = 5, Bottom = 5 };
    Padding titlePadding = new Padding() { Left = 90, Top = 0, Right = 0, Bottom = 10 };
    FormatSettings formatSettings = new FormatSettings() { Prefix = "$", ThousandsSeparator="," };
}
<label>ASP .NET MVC Core Bubble Chart Example</label><br/><br/>
<jqx-chart style="width: 850px; height: 500px;" color-scheme="scheme02" show-legend="true" padding="padding" title-padding="titlePadding" title="Sales by City in Q1 and Q2, and YoY sales growth"
     description="(the size of the circles represents relative YoY growth)" source="Model">
    <jqx-chart-x-axis values-on-ticks="false" for="@item.City" ></jqx-chart-x-axis>
    <jqx-chart-value-axis unit-interval="50000" min-value="50000" max-value="350000">
        <jqx-chart-title text="Sales ($)"></jqx-chart-title>
        <jqx-chart-labels horizontal-aligment="HorizontalAlignment.Right" format-settings="formatSettings"></jqx-chart-labels>
    </jqx-chart-value-axis>
    <jqx-chart-series-groups>
        <jqx-chart-serie-group type="SerieType.Bubble">
            <jqx-chart-series>
                <jqx-chart-serie for="@item.SalesQ1" radius-for="@item.YoYGrowthQ1" min-radius="10" max-radius="30" display-text="Sales in Q1"></jqx-chart-serie>
                <jqx-chart-serie for="@item.SalesQ2" radius-for="@item.YoYGrowthQ2" min-radius="10" max-radius="30" display-text="Sales in Q2"></jqx-chart-serie>
            </jqx-chart-series>
        </jqx-chart-serie-group>
    </jqx-chart-series-groups>
</jqx-chart>
```

### CheckBox

The ```jqx-check-box``` tag helper adds a CheckBox component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC CheckBox Example";
}
<label>ASP .NET Core MVC CheckBox Example</label><br/><br/>
<form asp-action="CarFeatures" method="post">
    Choose Optional Features:
   @foreach (var item in Model.CarFeatures)
   {
        <jqx-check-box height="30" name="carFeatures" checked="@item.Value" theme="@ViewData["Theme"]">@item.Key</jqx-check-box>
   }
  <jqx-button type="submit" theme="@ViewData["Theme"]">Submit</jqx-button>
</form>
```

### Color Picker

The ```jqx-color-picker``` tag helper adds a Color Picker component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC ColorPicker Example";
}
<label>ASP .NET Core MVC ColorPicker Example</label><br/><br/>
<jqx-color-picker height="250" width="250" theme="@ViewData["Theme"]"></jqx-color-picker>
```

### Combo Box

The ```jqx-combo-box``` tag helper adds a ComboBox component to a web page.

```html
@model IEnumerable<jQWidgets.AspNet.Core.Models.SalesEmployee>
@{
    ViewData["Title"] = "ASP .NET MVC ComboBox Example";
}
@{
    var employee = Model.FirstOrDefault();
}
<label>ASP .NET Core MVC ComboBox Example</label><br/><br/>
<jqx-combo-box for="@employee.Name" value-for="@employee.ID" selected-index="0" edit="@Url.Action("EditItem","TagHelpers")" create="@Url.Action("AddItem","TagHelpers")" delete="@Url.Action("DeleteItem","TagHelpers")" instance="listInstance()" theme="@ViewData["Theme"]" width="250" height="30" source="Model"></jqx-combo-box>
<div style="margin-top:30px;">
    <label>Add/Delete/Update</label>
    <table>
        <tr>
            <td style="padding:10px;" align="right">Name:</td>
            <td><jqx-input value="Peter Green" height="25" id="name"></jqx-input></td>
        </tr>
    </table>
</div>
<jqx-button style="margin-top:20px;" theme="@ViewData["Theme"]" on-click="addItem()">Add Item</jqx-button>
<jqx-button style="margin-top:20px;" theme="@ViewData["Theme"]" on-click="removeItem()">Delete Item</jqx-button>
<jqx-button style="margin-top:20px;" theme="@ViewData["Theme"]" on-click="updateItem()">Update Item</jqx-button>
<script>
    var list = {};
    function addItem() {
       list.addItem($("#name").val());
    }
    function removeItem() {
        var item = list.getSelectedItem();
        if (item)
        {
            list.removeItem(item);
        }
    }
    function updateItem() {
        var item = list.getSelectedItem();
        if (item)
        {
            list.updateItem({value: item.value, label: $("#name").val() }, item);
        }
    }
    function listInstance(instance) {
        list = instance;
    }
</script>
```

```
create - {{String}} which determines the URL called when a ComboBox item is added.
for - {{ModelExpression}} used for model binding and determines the label member.
value-for - {{ModelExpression}} used for model binding and determines the value member.
delete - {{String}} which determines the URL called when a ComboBox item is deleted.
edit - {{String}} which determines the URL called when a ComboBox item is updated.
instance - {{String}} which determines the javascript member within the Script tag which refers to the ComboBox's instance. This member is useful when you want to dynamically invoke API members of the Javascript component.
server-processing - {{Boolean}} which determines whether server processing is enabled.
source-id - {{String}} which determines the data source's ID member.
source-id-for - {{ModelExpression}} used for model binding and determines the data source's ID member.
source-root - {{String}} which determines the data source's Root member.
source-total-records - {{Integer}} which determines the data source's TotalRecords member.
source-url - {{String}} which determines the data source's URL.
source-model - {{Model}} which determines the data source's Model.
```

### Complex Input

The ```jqx-complex-input``` tag helper adds a Complex Input component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC Complex Input Example";
}
<label>ASP .NET Core MVC Complex Input Example</label><br/><br/>
<jqx-complex-input theme="@ViewData["Theme"]" width="250" height="25"></jqx-complex-input>
```

### DataTable

The ```jqx-data-table``` tag helper adds a DataTable component to a web page. 
The DataTable tag helper shares the same API members as the Javascript DataTable widget i.e all properties, methods and events can be used. 
Additional properties for the ```jqx-data-table``` tag helper are:

```
create - {{String}} which determines the URL called when a DataTable row is added.
datafield-for - {{ModelExpression}} used for model binding and determines the column's bound member.
delete - {{String}} which determines the URL called when a DataTable row is deleted.
edit - {{String}} which determines the URL called when the DataTable is edited.
instance - {{String}} which determines the javascript member within the Script tag which refers to the DataTable's instance. This member is useful when you want to dynamically invoke API members of the Javascript component.
server-processing - {{Boolean}} which determines whether server processing is enabled.
source-id - {{String}} which determines the data source's ID member.
source-id-for - {{ModelExpression}} used for model binding and determines the data source's ID member.
source-root - {{String}} which determines the data source's Root member.
source-total-records - {{Integer}} which determines the data source's TotalRecords member.
source-url - {{String}} which determines the data source's URL.
source-model - {{Model}} which determines the data source's Model.
```

```jqx-datatable-columns``` tag helper should be defined within the ```jqx-datatable``` tag helper and defines the DataTable columns collection. <br />
```jqx-datatable-column``` tag helper should be defined within the ```jqx-datatable-columns``` tag helper and defines a DataTable column. <br />
```jqx-datatable-column-groups``` tag helper should be defined within the ```jqx-datatable``` tag helper and defines the DataTable columns hierarchy. <br />
```jqx-datatable-column-group``` tag helper should be defined within the ```jqx-datatable-column-groups``` tag helper and defines a DataTable column group.

```html
@model IEnumerable<jQWidgets.AspNet.Core.Models.Employee>
@{
    ViewData["Title"] = "ASP .NET MVC DataTable Example";
}
<label>ASP .NET Core MVC DataTable Tag Helper Example</label><br/><br/>
<jqx-data-table theme="@ViewData["Theme"]" sortable="true" width="850" source="Model"> 
    <jqx-data-table-columns>
        <jqx-data-table-column column-group="name" dataField="FirstName" width="100" text="First Name"></jqx-data-table-column>
        <jqx-data-table-column column-group="name" dataField="LastName" width="100" text="Last Name"></jqx-data-table-column>
        <jqx-data-table-column dataField="Title" width="150"></jqx-data-table-column>
        <jqx-data-table-column dataField="Address" width="200"></jqx-data-table-column>
        <jqx-data-table-column dataField="City" width="150"></jqx-data-table-column>
        <jqx-data-table-column dataField="Country"></jqx-data-table-column>
    </jqx-data-table-columns>
    <jqx-data-table-column-groups>
        <jqx-data-table-column-group name="name" text="Name"></jqx-data-table-column-group>
    </jqx-data-table-column-groups>
</jqx-data-table>
```

### DateTimeInput

The ```jqx-datetime-input``` tag helper adds a DateTimeInput component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC DateTimeInput Example";
}
<label>Date Input</label>
<jqx-date-time-input format-string="F" show-time-button="true" theme="@ViewData["Theme"]" width="300" height="25"></jqx-date-time-input>
```

### Docking

The ```jqx-docking``` tag helper adds a Bullet Chart component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC Docking Example";
}
<label>ASP .NET Core MVC Docking Example</label><br/><br/>
<jqx-docking theme="@ViewData["Theme"]">
    <jqx-docking-panel>
        <jqx-docking-window>
            <jqx-docking-window-header>Title 1.1</jqx-docking-window-header>
            <jqx-docking-window-body><jqx-button>Content 1.1</jqx-button></jqx-docking-window-body>
        </jqx-docking-window>
        <jqx-docking-window>
            <jqx-docking-window-header>Title 1.2</jqx-docking-window-header>
            <jqx-docking-window-body><jqx-button>Content 1.2</jqx-button></jqx-docking-window-body>
        </jqx-docking-window>
    </jqx-docking-panel>
    <jqx-docking-panel>
        <jqx-docking-window>
            <jqx-docking-window-header>Title 2.1</jqx-docking-window-header>
            <jqx-docking-window-body><jqx-button>Content 2.1</jqx-button></jqx-docking-window-body>
        </jqx-docking-window>
        <jqx-docking-window>
            <jqx-docking-window-header>Title 2.2</jqx-docking-window-header>
            <jqx-docking-window-body><jqx-button>Content 2.2</jqx-button></jqx-docking-window-body>
        </jqx-docking-window>
    </jqx-docking-panel>
</jqx-docking>
```

```jqx-docking-panel``` tag helper defines a docking panel. <br />
```jqx-docking-window``` tag helper defines a docking window. <br />
```jqx-docking-window-header``` tag helper defines a docking window's header. <br />
```jqx-docking-window-body``` tag helper defines a docking window's body.

### Docking Layout

The jqx-docking-layout tag helper adds a Docking Layout component to a web page.

```html
@model IEnumerable<jQWidgets.AspNet.Core.Models.TreeItem>
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@{
    ViewData["Title"] = "ASP .NET MVC Docking Layout Example";
    // Create Layout Object.
    List<LayoutItem> layout = new List<LayoutItem>()
    {
        new LayoutItem()
        {
           Type = LayoutItemType.LayoutGroup,
          Orientation = Orientation.Horizontal,
          Items = new List<LayoutItem>()
          {
              new LayoutItem()
              {
                  Type = LayoutItemType.AutoHideGroup,
                  Alignment = Alignment.Left,
                  Width = "80",
                  UnpinnedWidth = "200",
                  Items = new List<LayoutItem>()
                  {
                      new LayoutItem()
                      {
                          Type = LayoutItemType.LayoutPanel,
                          Title = "Toolbox",
                          ContentContainer = "ToolboxPanel"
                      },
                      new LayoutItem()
                      {
                          Type = LayoutItemType.LayoutPanel,
                          Title = "Helper",
                          ContentContainer = "HelperPanel"
                      }
                  }
              },
             new LayoutItem()
             {
                Type = LayoutItemType.LayoutGroup,
                Orientation = Orientation.Vertical,
                Width = "500",
                Items = new List<LayoutItem>()
                {
                    new LayoutItem()
                    {
                        Type = LayoutItemType.DocumentGroup,
                        Height = "400",
                        MinHeight = "200",
                        Items = new List<LayoutItem>()
                        {
                            new LayoutItem()
                            {
                                Type = LayoutItemType.DocumentPanel,
                                Title = "Document 1",
                                ContentContainer = "Document1Panel"
                            },
                            new LayoutItem()
                            {
                                Type = LayoutItemType.DocumentPanel,
                                Title = "Document 2",
                                ContentContainer = "Document2Panel"
                            }
                        }
                    },
                    new LayoutItem()
                    {
                        Type = LayoutItemType.TabbedGroup,
                        Height = "200",
                        PinnedHeight = "30",
                        Items = new List<LayoutItem>()
                        {
                            new LayoutItem()
                            {
                                Type = LayoutItemType.LayoutPanel,
                                Title = "Error List",
                                ContentContainer = "ErrorListPanel"
                            }
                        }
                    }
                }
              },
            new LayoutItem()
            {
                Type = LayoutItemType.TabbedGroup,
                Width = "220",
                MinWidth = "200",
                Items = new List<LayoutItem>()
                {
                    new LayoutItem()
                    {
                        Type = LayoutItemType.LayoutPanel,
                        Title = "Solution Explorer",
                        ContentContainer = "SolutionExplorerPanel",
                        InitContent = "InitSolutionExplorerPanel()"
                    },
                    new LayoutItem()
                    {
                        Type = LayoutItemType.LayoutPanel,
                        Title = "Properties",
                        ContentContainer= "PropertiesPanel"
                    }
                }
            }
          }
        },
        new LayoutItem()
        {
            Type = LayoutItemType.FloatGroup,
            Width = "500",
            Height = "300",
            Position = new Position()
            {
                X = 350,
                Y = 250
            },
            Items = new List<LayoutItem>()
            {
                new LayoutItem()
                {
                    Type = LayoutItemType.LayoutPanel,
                    Title = "Output",
                    ContentContainer = "OutputPanel",
                    Selected = true
                }
            }
        }
    };
}
<script>

    function InitSolutionExplorerPanel() {
        $('#solutionExplorerTree')[0].setAttribute("initInstance", "true");
    }
</script>
<label>ASP .NET Core MVC Docking Layout Example</label><br/><br/>
<jqx-dockinglayout width="800" height="600" layout="@layout" theme="@ViewData["Theme"]">
    <!--The panel content divs can have a flat structure-->
    <!--autoHideGroup-->
    <div data-container="ToolboxPanel">
        List of tools
    </div>
    <div data-container="HelpPanel">
        Help topics
    </div>
    <!--documentGroup-->
    <div data-container="Document1Panel">
        Document 1 content
    </div>
    <div data-container="Document2Panel">
        Document 2 content
    </div>
    <!--bottom tabbedGroup-->
    <div data-container="ErrorListPanel">
        List of errors
    </div>
    <!--right tabbedGroup-->
    <div data-container="SolutionExplorerPanel">
        <jqx-tree initInstance="false" theme="@ViewData["Theme"]" id="solutionExplorerTree" width="190" itemsMember="Items" displayMember="Label" source="Model" style="border: none;">
        </jqx-tree>
    </div>
    <div data-container="PropertiesPanel">
        List of properties
    </div>
    <!--floatGroup-->
    <div data-container="OutputPanel">
        <div style="font-family: Consolas;">
            <p>
                Themes installation complete.
            </p>
            <p>
                List of installed stylesheet files. Include at least one stylesheet Theme file and
                the images folder:
            </p>
            <ul>
                <li>
                    styles/jqx.base.css: Stylesheet for the base Theme. The jqx.base.css file should
                    be always included in your project.
                </li>
                <li>styles/jqx.arctic.css: Stylesheet for the Arctic Theme</li>
                <li>styles/jqx.web.css: Stylesheet for the Web Theme</li>
                <li>styles/jqx.bootstrap.css: Stylesheet for the Bootstrap Theme</li>
                <li>styles/jqx.classic.css: Stylesheet for the Classic Theme</li>
                <li>styles/jqx.darkblue.css: Stylesheet for the DarkBlue Theme</li>
                <li>styles/jqx.energyblue.css: Stylesheet for the EnergyBlue Theme</li>
                <li>styles/jqx.shinyblack.css: Stylesheet for the ShinyBlack Theme</li>
                <li>styles/jqx.office.css: Stylesheet for the Office Theme</li>
                <li>styles/jqx.metro.css: Stylesheet for the Metro Theme</li>
                <li>styles/jqx.metrodark.css: Stylesheet for the Metro Dark Theme</li>
                <li>styles/jqx.orange.css: Stylesheet for the Orange Theme</li>
                <li>styles/jqx.summer.css: Stylesheet for the Summer Theme</li>
                <li>styles/jqx.black.css: Stylesheet for the Black Theme</li>
<script src="~/jqwidgets/jqxbuttons.js"></script>
<script src="~/jqwidgets/jqxscrollbar.js"></script>
<script src="~/jqwidgets/jqxpanel.js"></script>
<script src="~/jqwidgets/jqxribbon.js"></script>
<script src="~/jqwidgets/jqxlayout.js"></script>
<script src="~/jqwidgets/jqxtree.js"></script>
<script src="~/jqwidgets/jqxwindow.js"></script>
<script src="~/jqwidgets/jqxdockinglayout.js"></script>

@model IEnumerable<jQWidgets.AspNet.Core.Models.TreeItem>
@using jQWidgets.AspNetCore.Mvc.TagHelpers

@{
    ViewData["Title"] = "ASP .NET MVC Docking Layout Example";

    // Create Layout Object.
    List<LayoutItem> layout = new List<LayoutItem>()
    {
        new LayoutItem()
        {
           Type = LayoutItemType.LayoutGroup,
          Orientation = Orientation.Horizontal,
          Items = new List<LayoutItem>()
          {
              new LayoutItem()
              {
                  Type = LayoutItemType.AutoHideGroup,
                  Alignment = Alignment.Left,
                  Width = "80",
                  Unpinned-width = "200",
                  Items = new List<LayoutItem>()
                  {
                      new LayoutItem()
                      {
                          Type = LayoutItemType.LayoutPanel,
                          Title = "Toolbox",
                          ContentContainer = "ToolboxPanel"
                      },
                      new LayoutItem()
                      {
                          Type = LayoutItemType.LayoutPanel,
                          Title = "Helper",
                          ContentContainer = "HelperPanel"
                      }
                  }
              },
             new LayoutItem()
             {
                Type = LayoutItemType.LayoutGroup,
                Orientation = Orientation.Vertical,
                Width = "500",
                Items = new List<LayoutItem>()
                {
                    new LayoutItem()
                    {
                        Type = LayoutItemType.DocumentGroup,
                        Height = "400",
                        MinHeight = "200",
                        Items = new List<LayoutItem>()
                        {
                            new LayoutItem()
                            {
                                Type = LayoutItemType.DocumentPanel,
                                Title = "Document 1",
                                ContentContainer = "Document1Panel"
                            },
                            new LayoutItem()
                            {
                                Type = LayoutItemType.DocumentPanel,
                                Title = "Document 2",
                                ContentContainer = "Document2Panel"
                            }
                        }
                    },
                    new LayoutItem()
                    {
                        Type = LayoutItemType.TabbedGroup,
                        Height = "200",
                        PinnedHeight = "30",
                        Items = new List<LayoutItem>()
                        {
                            new LayoutItem()
                            {
                                Type = LayoutItemType.LayoutPanel,
                                Title = "Error List",
                                ContentContainer = "ErrorListPanel"
                            }
                        }
                    }
                }
              },
            new LayoutItem()
            {
                Type = LayoutItemType.TabbedGroup,
                Width = "220",
                MinWidth = "200",
                Items = new List<LayoutItem>()
                {
                    new LayoutItem()
                    {
                        Type = LayoutItemType.LayoutPanel,
                        Title = "Solution Explorer",
                        ContentContainer = "SolutionExplorerPanel",
                        InitContent = "InitSolutionExplorerPanel()"
                    },
                    new LayoutItem()
                    {
                        Type = LayoutItemType.LayoutPanel,
                        Title = "Properties",
                        ContentContainer= "PropertiesPanel"
                    }
                }
            }
          }
        },
        new LayoutItem()
        {
            Type = LayoutItemType.FloatGroup,
            Width = "500",
            Height = "300",
            Position = new Position()
            {
                X = 350,
                Y = 250
            },
            Items = new List<LayoutItem>()
            {
                new LayoutItem()
                {
                    Type = LayoutItemType.LayoutPanel,
                    Title = "Output",
                    ContentContainer = "OutputPanel",
                    Selected = true
                }
            }
        }
    };
}

<script>
 
    function InitSolutionExplorerPanel() {
        $('#solutionExplorerTree')[0].setAttribute("initInstance", "true");       
    }

</script>
<jqx-docking-layout width="800" height="600" layout="@layout" theme="@ViewData["Theme"]">
    <!--The panel content divs can have a flat structure-->
    <!--auto-hideGroup-->
    <div data-container="ToolboxPanel">
        List of tools
    </div>
    <div data-container="HelpPanel">
        Help topics
    </div>
    <!--documentGroup-->
    <div data-container="Document1Panel">
        Document 1 content
    </div>
    <div data-container="Document2Panel">
        Document 2 content
    </div>
    <!--bottom tabbedGroup-->
    <div data-container="ErrorListPanel">
        List of errors
    </div>
    <!--right tabbedGroup-->
    <div data-container="SolutionExplorerPanel">
        <jqx-tree initInstance="false" theme="@ViewData["Theme"]" id="solutionExplorerTree" width="190" itemsMember="Items" display-member="Label" source="Model" style="border: none;">
        </jqx-tree>
    </div>
    <div data-container="PropertiesPanel">
        List of properties
    </div>
    <!--floatGroup-->
    <div data-container="OutputPanel">
        <div style="font-family: Consolas;">
            <p>
                Themes installation complete.
            </p>
            <p>
                List of installed stylesheet files. Include at least one stylesheet Theme file and
                the images folder:
            </p>
            <ul>
                <li>
                    styles/jqx.base.css: Stylesheet for the base Theme. The jqx.base.css file should
                    be always included in your project.
                </li>
                <li>styles/jqx.arctic.css: Stylesheet for the Arctic Theme</li>
                <li>styles/jqx.web.css: Stylesheet for the Web Theme</li>
                <li>styles/jqx.bootstrap.css: Stylesheet for the Bootstrap Theme</li>
                <li>styles/jqx.classic.css: Stylesheet for the Classic Theme</li>
                <li>styles/jqx.darkblue.css: Stylesheet for the DarkBlue Theme</li>
                <li>styles/jqx.energyblue.css: Stylesheet for the EnergyBlue Theme</li>
                <li>styles/jqx.shinyblack.css: Stylesheet for the ShinyBlack Theme</li>
                <li>styles/jqx.office.css: Stylesheet for the Office Theme</li>
                <li>styles/jqx.metro.css: Stylesheet for the Metro Theme</li>
                <li>styles/jqx.metrodark.css: Stylesheet for the Metro Dark Theme</li>
                <li>styles/jqx.orange.css: Stylesheet for the Orange Theme</li>
                <li>styles/jqx.summer.css: Stylesheet for the Summer Theme</li>
                <li>styles/jqx.black.css: Stylesheet for the Black Theme</li>
                <li>styles/jqx.fresh.css: Stylesheet for the Fresh Theme</li>
                <li>styles/jqx.highcontrast.css: Stylesheet for the HighContrast Theme</li>
                <li>styles/jqx.blackberry.css: Stylesheet for the Blackberry Theme</li>
                <li>styles/jqx.android.css: Stylesheet for the Android Theme</li>
                <li>styles/jqx.mobile.css: Stylesheet for the Mobile Theme</li>
                <li>styles/jqx.windowsphone.css: Stylesheet for the Windows Phone Theme</li>
                <li>styles/jqx.ui-darkness.css: Stylesheet for the UI Darkness Theme</li>
                <li>styles/jqx.ui-lightness.css: Stylesheet for the UI Lightness Theme</li>
                <li>styles/jqx.ui-le-frog.css: Stylesheet for the UI Le Frog Theme</li>
                <li>styles/jqx.ui-overcast.css: Stylesheet for the UI Overcast Theme</li>
                <li>styles/jqx.ui-redmond.css: Stylesheet for the UI Redmond Theme</li>
                <li>styles/jqx.ui-smoothness.css: Stylesheet for the UI Smoothness Theme</li>
                <li>styles/jqx.ui-start.css: Stylesheet for the UI Start Theme</li>
                <li>styles/jqx.ui-sunny.css: Stylesheet for the UI Sunny Theme</li>
                <li>styles/images: contains images referenced in the stylesheet files</li>
            </ul>
        </div>
    </div>
</jqx-docking-layout>
```

### DropDownList


The ```jqx-dropdown-list``` tag helper adds a DropDownList component to a web page.

```
create - {{String}} which determines the URL called when a DropDownList item is added.
for - {{ModelExpression}} used for model binding and determines the label member.
value-for - {{ModelExpression}} used for model binding and determines the value member.
delete - {{String}} which determines the URL called when a DropDownList item is deleted.
edit - {{String}} which determines the URL called when a DropDownList item is updated.
instance - {{String}} which determines the javascript member within the Script tag which refers to the DropDownList's instance. This member is useful when you want to dynamically invoke API members of the Javascript component.
server-processing - {{Boolean}} which determines whether server processing is enabled.
source-id - {{String}} which determines the data source's ID member.
source-id-for - {{ModelExpression}} used for model binding and determines the data source's ID member.
source-root - {{String}} which determines the data source's Root member.
source-total-records - {{Integer}} which determines the data source's TotalRecords member.
source-url - {{String}} which determines the data source's URL.
source-model - {{Model}} which determines the data source's Model.
```

```html
<script src="~/jqwidgets/jqxbuttons.js"></script>
<script src="~/jqwidgets/jqxscrollbar.js"></script>
<script src="~/jqwidgets/jqxinput.js"></script>
<script src="~/jqwidgets/jqxlistbox.js"></script>
<script src="~/jqwidgets/jqxdropdownlist.js"></script>

@model IEnumerable<jQWidgets.AspNet.Core.Models.SalesEmployee>

@{
    ViewData["Title"] = "ASP .NET MVC DropDownList Example";
}
@{
    var employee = Model.FirstOrDefault();
}
<jqx-drop-down-list for="@employee.Name" value-for="@employee.ID" selected-index="0" edit="@Url.Action("EditItem","TagHelpers")" create="@Url.Action("AddItem","TagHelpers")" delete="@Url.Action("DeleteItem","TagHelpers")" instance="listInstance()" theme="@ViewData["Theme"]" width="250" height="30" source="Model"></jqx-drop-down-list>
<div style="margin-top:30px;">
    <label>Add/Delete/Update</label>
    <table>
        <tr>
            <td style="padding:10px;" align="right">Name:</td>
            <td><jqx-input value="Peter Green" height="25" id="name"></jqx-input></td>
        </tr>
    </table>
</div>
<jqx-button style="margin-top:20px;" theme="@ViewData["Theme"]" on-click="addItem()">Add Item</jqx-button>
<jqx-button style="margin-top:20px;" theme="@ViewData["Theme"]" on-click="removeItem()">Delete Item</jqx-button>
<jqx-button style="margin-top:20px;" theme="@ViewData["Theme"]" on-click="updateItem()">Update Item</jqx-button>
<script>
    var list = {};
    function addItem() {
       list.addItem($("#name").val());
    }

    function removeItem() {
        var item = list.getSelectedItem();
        if (item)
        {
            list.removeItem(item);
        }
    }

    function updateItem() {
        var item = list.getSelectedItem();
        if (item)
        {
            list.updateItem({value: item.value, label: $("#name").val() }, item);
        }
    }

    function listInstance(instance) {
        list = instance;
    }
</script>
```

### Editor

The ```jqx-editor``` tag helper adds Editor component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC Editor Example";
}
<label>ASP .NET Core MVC Editor Example</label><br/><br/>
<jqx-editor theme="@ViewData["Theme"]" width="800" height="400"></jqx-editor>
```

### Expander

The ```jqx-expander``` tag helper adds Expander component to a web page.
@{
    ViewData["Title"] = "ASP .NET MVC Expander Example";
}
<label>ASP .NET Core MVC Expander Example</label><br/><br/>
<jqx-expander width="500" theme="@ViewData["Theme"]">
    <jqx-expander-header>Header</jqx-expander-header>
    <jqx-expander-body>
       <jqx-button style="margin:5px;" theme="@ViewData["Theme"]">Button 1</jqx-button>
       <jqx-button style="margin:5px;" theme="@ViewData["Theme"]">Button 2</jqx-button>
       <jqx-button style="margin:5px;" theme="@ViewData["Theme"]">Button 3</jqx-button>
   </jqx-expander-body>
</jqx-expander>
jqx-expander-header tag helper defines the expander's header. jqx-expander-body tag helper defines the expander's body.
FileUpload

The jqx-file-upload tag helper adds a File Upload component to a web page.
@{
    ViewData["Title"] = "ASP .NET MVC FileUpload Example";
}
<label>ASP .NET Core MVC File Upload Example</label><br/><br/>
<jqx-file-upload width="300" multiple-files-upload="false" upload-url="@Url.Action("UploadFile", "TagHelpers")", fileInputName="fileToUpload" ></jqx-file-upload>

### Formatted Input

The ```jqx-formatted-input``` tag helper adds a Formatted Input component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC Formatted Input Example";
}
<label>ASP .NET Core MVC Formatted Input Example</label><br/><br/>
<jqx-formatted-input theme="@ViewData["Theme"]" width="250" height="25"></jqx-formatted-input>
```

### Gauge

The ```jqx-gauge``` tag helper adds a Gauge component to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers;
@{
    ViewData["Title"] = "ASP .NET MVC Gauge Example";
    List<GaugeRange> ranges = new List<GaugeRange>()
    {
        new GaugeRange() {StartValue = 0, EndValue = 55, StartWidth = 1, EndWidth = 5, Style = new GaugeStyle() {Fill = "#4bb648", Stroke = "#4bb648" }},
        new GaugeRange() {StartValue = 55, EndValue = 110, StartWidth = 5, EndWidth = 10, Style = new GaugeStyle() {Fill = "#fbd109", Stroke = "#fbd109" }},
        new GaugeRange() {StartValue = 110, EndValue = 165, StartWidth = 10, EndWidth = 13, Style = new GaugeStyle() {Fill = "#ff8000", Stroke = "#ff8000"} },
        new GaugeRange() {StartValue = 165, EndValue = 220, StartWidth = 13, EndWidth = 16, Style = new GaugeStyle() {Fill = "#e02629", Stroke = "#e02629" } }
    };
    GaugeTicks ticksMinor = new GaugeTicks() { Interval = 5, Size = "5%" };
    GaugeTicks ticksMajor = new GaugeTicks() { Interval = 10, Size = "9%" };
}
<label>ASP .NET Core MVC Gauge Tag Helper Example</label><br/><br/>
<jqx-gauge ranges="ranges" ticks-minor="ticksMinor" ticks-major="ticksMajor" value="50" color-scheme="scheme05" animation-duration="1200"></jqx-gauge>
```

### Input

The ```jqx-input``` tag helper adds an Input component to a web page.

```
create - {{String}} which determines the URL called when a Input item is added.
for - {{ModelExpression}} used for model binding and determines the label member.
value-for - {{ModelExpression}} used for model binding and determines the value member.
delete - {{String}} which determines the URL called when a Input item is deleted.
edit - {{String}} which determines the URL called when a Input item is updated.
instance - {{String}} which determines the javascript member within the Script tag which refers to the Input's instance. This member is useful when you want to dynamically invoke API members of the Javascript component.
server-processing - {{Boolean}} which determines whether server processing is enabled.
source-id - {{String}} which determines the data source's ID member.
source-id-for - {{ModelExpression}} used for model binding and determines the data source's ID member.
source-root - {{String}} which determines the data source's Root member.
source-total-records - {{Integer}} which determines the data source's TotalRecords member.
source-url - {{String}} which determines the data source's URL.
source-model - {{Model}} which determines the data source's Model.
```

```html
<script src="~/jqwidgets/jqxinput.js"></script>


@model IEnumerable<jQWidgets.AspNet.Core.Models.SalesEmployee>

@{
    ViewData["Title"] = "ASP .NET MVC Input Example";
}
<script>
    function change(event) {
        var args = event.args;
        document.getElementById("log").innerHTML = "Label: " + args.label + ", Value: " + args.value;;
    }
</script>
<label>Enter Name:</label>
<jqx-input on-change="change()" display-member="Name" selected-index="0" value-member="ID" theme="@ViewData["Theme"]" width="250" height="30" source="Model"></jqx-input>
(ex: An)
<br /><br />
<div id="log"></div>
```

### Kanban

The ```jqx-kanban``` tag helper adds a Kanban component to a web page.

```html
<script src="~/jqwidgets/jqxkanban.js"></script>
<script src="~/jqwidgets/jqxsortable.js"></script>

@model jQWidgets.AspNet.Core.Models.jQWidgetsDemosContext
@using jQWidgets.AspNetCore.Mvc.TagHelpers

@{
    ViewData["Title"] = "ASP .NET MVC Kanban Example";
    Dictionary<string, string> mappings = new Dictionary<string, string>();
    mappings["Id"] = "id";
    mappings["State"] = "status";
    mappings["Text"] = "label";
    mappings["Label"] = "label";
    mappings["Tags"] = "tags";
    mappings["Hex"] = "color";
    mappings["ResourceId"] = "resourceId";
    mappings["Name"] = "name";
    mappings["Image"] = "image";
}

<script>


</script>

<jqx-kanban mappings="mappings" resources="Model.KanbanResources" source="Model.KanbanDataItems" width="850">
    <jqx-kanban-columns>
        <jqx-kanban-column text="Backlog" dataField="New"></jqx-kanban-column>
        <jqx-kanban-column text="In Progress" dataField="Work"></jqx-kanban-column>
        <jqx-kanban-column text="Done" dataField="Done"></jqx-kanban-column>
</jqx-kanban-columns>
</jqx-kanban>
```

### Knob

The ```jqx-knob``` tag helper adds a Knob component to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers;
@{
<script src="~/jqwidgets/jqxknob.js"></script>

@using jQWidgets.AspNetCore.Mvc.TagHelpers;
@{
    ViewData["Title"] = "ASP .NET MVC Knob Example";
    KnobMarks marks = new KnobMarks()
    {
        ColorProgress = new KnobColor() { Color = "#00a4e1", Border = "#00a4e1" },
        ColorRemaining = new KnobColor() { Color = "#grey", Border = "#grey" },
        Type = "line",
        Offset = "71%",
        Thickness = 3,
        Size = "6%",
        MajorSize = "9%",
        MajorInterval = 10,
        MinorInterval = 2
    };
    KnobStyle style = new KnobStyle()
    {
        Stroke = "#dfe3e9",
        StrokeWidth = 3,
        Fill = new KnobGradientFill() { Color = "#fefefe", GradientStops = new List<string>() { "[0, 1]", "[50, 0.9]", "[100, 1]" } }
    };

    KnobLabels labels = new KnobLabels()
    {
        Offset = "88%",
        Step = 10
    };
    KnobProgressBar progressBar = new KnobProgressBar()
    {
        Style = new KnobStyle() { Fill = new KnobGradientFill() { Color = "#00a4e1" }, Stroke = "grey" },
        Size = "9%",
        Offset = "60%",
        Background = new KnobStyle() { Fill = new KnobGradientFill() { Color = "gray" }, Stroke = "gray" }
    };
}
<jqx-knob min="0" max="100" value="60" start-angle="120" end-angle="420" rotation="clockwise"  progress-bar="progressBar" labels="labels" style="style" marks="marks"></jqx-knob>

```

### Layout

The ```jqx-layout``` tag helper adds a Layout component to a web page.

```html
<script src="~/jqwidgets/jqxbuttons.js"></script>
<script src="~/jqwidgets/jqxscrollbar.js"></script>
<script src="~/jqwidgets/jqxpanel.js"></script>
<script src="~/jqwidgets/jqxlayout.js"></script>
<script src="~/jqwidgets/jqxribbon.js"></script>
<script src="~/jqwidgets/jqxtree.js"></script>

@model IEnumerable<jQWidgets.AspNet.Core.Models.TreeItem>
@using jQWidgets.AspNetCore.Mvc.TagHelpers

@{
    ViewData["Title"] = "ASP .NET MVC Layout Example";

    // Create Layout Object.
    List<LayoutItem> layout = new List<LayoutItem>()
    {
        new LayoutItem()
        {
           Type = LayoutItemType.LayoutGroup,
          Orientation = Orientation.Horizontal,
          Items = new List<LayoutItem>()
          {
              new LayoutItem()
              {
                  Type = LayoutItemType.AutoHideGroup,
                  Alignment = Alignment.Left,
                  Width = "80",
                  UnpinnedWidth = "200",
                  Items = new List<LayoutItem>()
                  {
                      new LayoutItem()
                      {
                          Type = LayoutItemType.LayoutPanel,
                          Title = "Toolbox",
                          ContentContainer = "ToolboxPanel"
                      },
                      new LayoutItem()
                      {
                          Type = LayoutItemType.LayoutPanel,
                          Title = "Helper",
                          ContentContainer = "HelperPanel"
                      }
                  }
              },
             new LayoutItem()
             {
                Type = LayoutItemType.LayoutGroup,
                Orientation = Orientation.Vertical,
                Width = "500",
                Items = new List<LayoutItem>()
                {
                    new LayoutItem()
                    {
                        Type = LayoutItemType.DocumentGroup,
                        Height = "400",
                        MinHeight = "200",
                        Items = new List<LayoutItem>()
                        {
                            new LayoutItem()
                            {
                                Type = LayoutItemType.DocumentPanel,
                                Title = "Document 1",
                                ContentContainer = "Document1Panel"
                            },
                            new LayoutItem()
                            {
                                Type = LayoutItemType.DocumentPanel,
                                Title = "Document 2",
                                ContentContainer = "Document2Panel"
                            }
                        }
                    },
                    new LayoutItem()
                    {
                        Type = LayoutItemType.TabbedGroup,
                        Height = "200",
                        PinnedHeight = "30",
                        Items = new List<LayoutItem>()
                        {
                            new LayoutItem()
                            {
                                Type = LayoutItemType.LayoutPanel,
                                Title = "Error List",
                                ContentContainer = "ErrorListPanel"
                            }
                        }
                    }
                }
              },
            new LayoutItem()
            {
                Type = LayoutItemType.TabbedGroup,
                Width = "220",
                MinWidth = "200",
                Items = new List<LayoutItem>()
                {
                    new LayoutItem()
                    {
                        Type = LayoutItemType.LayoutPanel,
                        Title = "Solution Explorer",
                        ContentContainer = "SolutionExplorerPanel",
                        InitContent = "InitSolutionExplorerPanel()"
                    },
                    new LayoutItem()
                    {
                        Type = LayoutItemType.LayoutPanel,
                        Title = "Properties",
                        ContentContainer= "PropertiesPanel"
                    }
                }
            }
          }
        }
    };
}

<script>
 
    function InitSolutionExplorerPanel() {
        $('#solutionExplorerTree')[0].setAttribute("init-instance", "true");       
    }

</script>
<jqx-layout width="800" height="600" layout="@layout" theme="@ViewData["Theme"]">
    <!--The panel content divs can have a flat structure-->
    <!--auto-hideGroup-->
    <div data-container="ToolboxPanel">
        List of tools
    </div>
    <div data-container="HelpPanel">
        Help topics
    </div>
    <!--documentGroup-->
    <div data-container="Document1Panel">
        Document 1 content
    </div>
    <div data-container="Document2Panel">
        Document 2 content
    </div>
    <!--bottom tabbedGroup-->
    <div data-container="ErrorListPanel">
        List of errors
    </div>
    <!--right tabbedGroup-->
    <div data-container="SolutionExplorerPanel">
        <jqx-tree init-instance="false" theme="@ViewData["Theme"]" id="solutionExplorerTree" width="190" items-member="Items" display-member="Label" source="Model" style="border: none;">
        </jqx-tree>
    </div>
    <div data-container="PropertiesPanel">
        List of properties
    </div>
    <!--floatGroup-->
    <div data-container="OutputPanel">
        <div style="font-family: Consolas;">
            <p>
                Themes installation complete.
            </p>
            <p>
                List of installed stylesheet files. Include at least one stylesheet Theme file and
                the images folder:
            </p>
            <ul>
                <li>
                    styles/jqx.base.css: Stylesheet for the base Theme. The jqx.base.css file should
                    be always included in your project.
                </li>
                <li>styles/jqx.arctic.css: Stylesheet for the Arctic Theme</li>
                <li>styles/jqx.web.css: Stylesheet for the Web Theme</li>
                <li>styles/jqx.bootstrap.css: Stylesheet for the Bootstrap Theme</li>
                <li>styles/jqx.classic.css: Stylesheet for the Classic Theme</li>
                <li>styles/jqx.darkblue.css: Stylesheet for the DarkBlue Theme</li>
                <li>styles/jqx.energyblue.css: Stylesheet for the EnergyBlue Theme</li>
                <li>styles/jqx.shinyblack.css: Stylesheet for the ShinyBlack Theme</li>
                <li>styles/jqx.office.css: Stylesheet for the Office Theme</li>
                <li>styles/jqx.metro.css: Stylesheet for the Metro Theme</li>
                <li>styles/jqx.metrodark.css: Stylesheet for the Metro Dark Theme</li>
                <li>styles/jqx.orange.css: Stylesheet for the Orange Theme</li>
                <li>styles/jqx.summer.css: Stylesheet for the Summer Theme</li>
                <li>styles/jqx.black.css: Stylesheet for the Black Theme</li>
                <li>styles/jqx.fresh.css: Stylesheet for the Fresh Theme</li>
                <li>styles/jqx.highcontrast.css: Stylesheet for the HighContrast Theme</li>
                <li>styles/jqx.blackberry.css: Stylesheet for the Blackberry Theme</li>
                <li>styles/jqx.android.css: Stylesheet for the Android Theme</li>
                <li>styles/jqx.mobile.css: Stylesheet for the Mobile Theme</li>
                <li>styles/jqx.windowsphone.css: Stylesheet for the Windows Phone Theme</li>
                <li>styles/jqx.ui-darkness.css: Stylesheet for the UI Darkness Theme</li>
                <li>styles/jqx.ui-lightness.css: Stylesheet for the UI Lightness Theme</li>
                <li>styles/jqx.ui-le-frog.css: Stylesheet for the UI Le Frog Theme</li>
                <li>styles/jqx.ui-overcast.css: Stylesheet for the UI Overcast Theme</li>
                <li>styles/jqx.ui-redmond.css: Stylesheet for the UI Redmond Theme</li>
                <li>styles/jqx.ui-smoothness.css: Stylesheet for the UI Smoothness Theme</li>
                <li>styles/jqx.ui-start.css: Stylesheet for the UI Start Theme</li>
                <li>styles/jqx.ui-sunny.css: Stylesheet for the UI Sunny Theme</li>
                <li>styles/images: contains images referenced in the stylesheet files</li>
            </ul>
        </div>
    </div>
</jqx-layout>

```

### Linear Gauge

The ```jqx-linear-gauge``` tag helper adds a Linear Gauge component to a web page.

```html
<script src="~/jqwidgets/jqxgauge.js"></script>

@using jQWidgets.AspNetCore.Mvc.TagHelpers;
@{
    ViewData["Title"] = "ASP .NET MVC Linear Gauge Example";
    GaugeLabels labels = new GaugeLabels() { Interval = 20, FormatValue = "formatValue()" };
        List<GaugeRange> ranges = new List<GaugeRange>()
        {
            new GaugeRange() {StartValue = -10, EndValue = 10, Style = new GaugeStyle() {Fill = "#4bb648", Stroke = "#4bb648" }},
            new GaugeRange() {StartValue = 10, EndValue = 35, Style = new GaugeStyle() {Fill = "#fbd109", Stroke = "#fbd109" }},
            new GaugeRange() {StartValue = 35, EndValue = 60, Style = new GaugeStyle() {Fill = "#ff8000", Stroke = "#ff8000"}}
        };
    GaugeTicks ticksMinor = new GaugeTicks() { Interval = 2.5, Size = "5%", Style = new GaugeStyle() { StrokeWidth = 1, Stroke = "#aaaaaa" } };
    GaugeTicks ticksMajor = new GaugeTicks() { Interval = 10, Size = "10%" };
    GaugePointer pointer = new GaugePointer() { Size = "5%" };
}

<script>
    function formatValue(value, position) {
        if (position === 'far') {
            value = (9 / 5) * value + 32;
            if (value === -76) {
                return 'F';
            }
            return value + '';
        }
        if (value === -60) {
            return 'C';
        }
        return value + '';
    }
</script>
<jqx-linear-gauge width="100" max="60" orientation="Orientation.Vertical" height="350" pointer="pointer" ranges="ranges" labels="labels" ticks-minor="ticksMinor" ticks-major="ticksMajor" value="50" colorScheme="scheme05" animationDuration="1200"></jqx-linear-gauge>

Link Button

The jqx-link-button tag helper adds a Link Button component to a web page.
```html
<script src="~/jqwidgets/jqxlinkbutton.js"></script>

@{
    ViewData["Title"] = "ASP .NET MVC Link Button Example";
}

<jqx-link-button theme="@ViewData["Theme"]" target="_blank" href="http://www.jqwidgets.com">Link Button</jqx-link-button>
```

### List Box

The ```jqx-list-box``` tag helper adds a List Box component to a web page.

```html
<script src="~/jqwidgets/jqxbuttons.js"></script>
<script src="~/jqwidgets/jqxscrollbar.js"></script>
<script src="~/jqwidgets/jqxlistbox.js"></script>
<script src="~/jqwidgets/jqxinput.js"></script>

@model IEnumerable<jQWidgets.AspNet.Core.Models.SalesEmployee>

@{
    ViewData["Title"] = "ASP .NET MVC ListBox Example";
}
@{
    var employee = Model.FirstOrDefault();
}
<jqx-list-box display-member="Name" selected-index="0" edit="@Url.Action("EditItem","TagHelpers")" create="@Url.Action("AddItem","TagHelpers")" delete="@Url.Action("DeleteItem","TagHelpers")" instance="listInstance()" value-member="ID" theme="@ViewData["Theme"]" width="250" height="300" source="Model"></jqx-list-box>
<div style="margin-top:30px;">
    <label>Add/Delete/Update</label>
    <table>
        <tr>
            <td style="padding:10px;" align="right">Name:</td>
            <td><jqx-input value="Peter Green" height="25" id="name"></jqx-input></td>
        </tr>
    </table>
</div>
<jqx-button style="margin-top:20px;" theme="@ViewData["Theme"]" on-click="addItem()">Add Item</jqx-button>
<jqx-button style="margin-top:20px;" theme="@ViewData["Theme"]" on-click="removeItem()">Delete Item</jqx-button>
<jqx-button style="margin-top:20px;" theme="@ViewData["Theme"]" on-click="updateItem()">Update Item</jqx-button>
<script>
    var list = {};
    function addItem() {
       list.addItem($("#name").val());
    }

    function removeItem() {
        var item = list.getSelectedItem();
        if (item)
        {
            list.removeItem(item);
        }
    }

    function updateItem() {
        var item = list.getSelectedItem();
        if (item)
        {
            list.updateItem({value: item.value, label: $("#name").val() }, item);
        }
    }

    function listInstance(instance) {
        list = instance;
    }
</script>
```

### List Menu

The ```jqx-list-menu``` tag helper adds a List Menu component to a web page.

```html
<script src="~/jqwidgets/jqxbuttons.js"></script>
<script src="~/jqwidgets/jqxscrollbar.js"></script>
<script src="~/jqwidgets/jqxpanel.js"></script>
<script src="~/jqwidgets/jqxlistmenu.js"></script>

@using jQWidgets.AspNetCore.Mvc.TagHelpers

@{
    ViewData["Title"] = "ASP .NET MVC ListMenu Example";
}


<jqx-list-menu theme="@ViewData["Theme"]" enable-scrolling="false" width="350">
    <jqx-list-menu-items>
      <jqx-list-menu-item>
            OSI
          <jqx-list-menu-items>
              <jqx-list-menu-item>
                  Application Layer
                  <jqx-list-menu-items>
                      <jqx-list-menu-item>SIP</jqx-list-menu-item>
                      <jqx-list-menu-item>DNS</jqx-list-menu-item>
                      <jqx-list-menu-item>FTP</jqx-list-menu-item>
                      <jqx-list-menu-item>RTP</jqx-list-menu-item>
                      <jqx-list-menu-item>DHCP</jqx-list-menu-item>
                  </jqx-list-menu-items>
              </jqx-list-menu-item>
          </jqx-list-menu-items>         
        </jqx-list-menu-item>
        <jqx-list-menu-item>
            TCP/IP
            <jqx-list-menu-items>
                <jqx-list-menu-item>
                    Application layer
                    <jqx-list-menu-items>
                        <jqx-list-menu-item>DHCP</jqx-list-menu-item>
                        <jqx-list-menu-item>DNS</jqx-list-menu-item>
                        <jqx-list-menu-item>FTP</jqx-list-menu-item>
                        <jqx-list-menu-item>HTTP</jqx-list-menu-item>
                        <jqx-list-menu-item>IMAP</jqx-list-menu-item>
                        <jqx-list-menu-item>LDAP</jqx-list-menu-item>
                        <jqx-list-menu-item>XMPP</jqx-list-menu-item>
                        <jqx-list-menu-item>SSH</jqx-list-menu-item>
                        <jqx-list-menu-item>RIP</jqx-list-menu-item>
                    </jqx-list-menu-items>
                </jqx-list-menu-item>
                <jqx-list-menu-item>
                    Transport layer
                    <jqx-list-menu-items>
                        <jqx-list-menu-item>TCP</jqx-list-menu-item>
                        <jqx-list-menu-item>UDP</jqx-list-menu-item>
                        <jqx-list-menu-item>SCTP</jqx-list-menu-item>
                    </jqx-list-menu-items>
                </jqx-list-menu-item>
                <jqx-list-menu-item>
                    Internet layer
                    <jqx-list-menu-items>
                        <jqx-list-menu-item>IP</jqx-list-menu-item>
                        <jqx-list-menu-item>ICMP</jqx-list-menu-item>
                        <jqx-list-menu-item>ECN</jqx-list-menu-item>
                    </jqx-list-menu-items>
                </jqx-list-menu-item>
                <jqx-list-menu-item>
                    Link layer
                    <jqx-list-menu-items>
                        <jqx-list-menu-item>ARP</jqx-list-menu-item>
                        <jqx-list-menu-item>NDP</jqx-list-menu-item>
                        <jqx-list-menu-item>DSL</jqx-list-menu-item>
                    </jqx-list-menu-items>
                </jqx-list-menu-item>
            </jqx-list-menu-items>
        </jqx-list-menu-item>
    </jqx-list-menu-items>
</jqx-list-menu>

```

### Masked Input

The ```jqx-masked-input``` tag helper adds a Masked Input component to a web page.

```html
<script src="~/jqwidgets/jqxmaskedinput.js"></script>

@{
    ViewData["Title"] = "ASP .NET MVC MaskedInput Example";
}
    <div style='margin-top: 10px;'>
        Numeric
    </div>
    <jqx-masked-input width="250" style='margin-top: 3px;' id='numericInput'></jqx-masked-input>
    <div style='margin-top: 10px;'>
        Zip Code
    </div>
    <jqx-masked-input width="250" mask="#####-####" style='margin-top: 3px;' id='zipCodeInput'></jqx-masked-input>
    <div style='margin-top: 10px;'>
        SSN
    </div>
    <jqx-masked-input width="250" mask="###-##-####" style='margin-top: 3px;' id='ssnInput'></jqx-masked-input>
    <div style='margin-top: 10px;'>
        Phone Number
    </div>
    <jqx-masked-input width="250" mask="(###)###-####" style='margin-top: 3px;' id='phoneInput'> </jqx-masked-input>
    <div style='margin-top: 10px;'>
        Disabled
    </div>
    <jqx-masked-input width="250" disabled="true"  style='margin-top: 3px;' id='disabledInput'></jqx-masked-input>
```

### Menu

The ```jqx-menu``` tag helper adds a Menu component to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@{
    ViewData["Title"] = "ASP .NET MVC Menu Example";
}
<label>ASP .NET Core MVC Menu Tag Helper Example</label><br/><br/>
<jqx-menu theme="@ViewData["Theme"]">
    <jqx-menu-items>
        <jqx-menu-item><a href="#Home">Home</a></jqx-menu-item>
        <jqx-menu-item>
            Solutions
            <jqx-menu-items style='width: 250px;'>
                <jqx-menu-item><a href="#Education">Education</a></jqx-menu-item>
                <jqx-menu-item><a href="#Financial">Financial services</a></jqx-menu-item>
                <jqx-menu-item><a href="#Government">Government</a></jqx-menu-item>
                <jqx-menu-item><a href="#Manufacturing">Manufacturing</a></jqx-menu-item>
                <jqx-menu-item type='separator'></jqx-menu-item>
                <jqx-menu-item>
                    Software Solutions
                    <jqx-menu-items style='width: 220px;'>
                        <jqx-menu-item><a href="#ConsumerPhoto">Consumer photo and video</a></jqx-menu-item>
                        <jqx-menu-item><a href="#Mobile">Mobile</a></jqx-menu-item>
                        <jqx-menu-item><a href="#RIA">Rich Internet apps</a></jqx-menu-item>
                        <jqx-menu-item><a href="#TechnicalCommunication">Technical communication</a></jqx-menu-item>
                        <jqx-menu-item><a href="#Training">Training and eLearning</a></jqx-menu-item>
                        <jqx-menu-item><a href="#WebConferencing">Web conferencing</a></jqx-menu-item>
                    </jqx-menu-items>
                </jqx-menu-item>
                <jqx-menu-item><a href="#">All industries and solutions</a></jqx-menu-item>
            </jqx-menu-items>
        </jqx-menu-item>
        <jqx-menu-item>
            Products
            <jqx-menu-items>
                <jqx-menu-item><a href="#PCProducts">PC products</a></jqx-menu-item>
                <jqx-menu-item><a href="#MobileProducts">Mobile products</a></jqx-menu-item>
                <jqx-menu-item><a href="#AllProducts">All products</a></jqx-menu-item>
            </jqx-menu-items>
        </jqx-menu-item>
        <jqx-menu-item>
            Support
            <jqx-menu-items style='width: 200px;'>
                <jqx-menu-item><a href="#SupportHome">Support home</a></jqx-menu-item>
                <jqx-menu-item><a href="#CustomerService">Customer Service</a></jqx-menu-item>
                <jqx-menu-item><a href="#KB">Knowledge base</a></jqx-menu-item>
                <jqx-menu-item><a href="#Books">Books</a></jqx-menu-item>
                <jqx-menu-item><a href="#Training">Training and certification</a></jqx-menu-item>
                <jqx-menu-item><a href="#SupportPrograms">Support programs</a></jqx-menu-item>
                <jqx-menu-item><a href="#Forums">Forums</a></jqx-menu-item>
                <jqx-menu-item><a href="#Documentation">Documentation</a></jqx-menu-item>
                <jqx-menu-item><a href="#Updates">Updates</a></jqx-menu-item>
            </jqx-menu-items>
        </jqx-menu-item>
        <jqx-menu-item>
            Communities
            <jqx-menu-items style='width: 200px;'>
                <jqx-menu-item><a href="#Designers">Designers</a></jqx-menu-item>
                <jqx-menu-item><a href="#Developers">Developers</a></jqx-menu-item>
                <jqx-menu-item><a href="#Educators">Educators and students</a></jqx-menu-item>
                <jqx-menu-item><a href="#Partners">Partners</a></jqx-menu-item>
                <jqx-menu-item type='separator'></jqx-menu-item>
                <jqx-menu-item>
                    By resource
                    <jqx-menu-items>
                        <jqx-menu-item><a href="#Labs">Labs</a></jqx-menu-item>
                        <jqx-menu-item><a href="#TV">TV</a></jqx-menu-item>
                        <jqx-menu-item><a href="#Forums">Forums</a></jqx-menu-item>
                        <jqx-menu-item><a href="#Exchange">Exchange</a></jqx-menu-item>
                        <jqx-menu-item><a href="#Blogs">Blogs</a></jqx-menu-item>
                        <jqx-menu-item><a href="#Experience Design">Experience Design</a></jqx-menu-item>
                    </jqx-menu-items>
                </jqx-menu-item>
            </jqx-menu-items>
        </jqx-menu-item>
        <jqx-menu-item>
            Company
            <jqx-menu-items style='width: 180px;'>
                <jqx-menu-item><a href="#About">About Us</a></jqx-menu-item>
                <jqx-menu-item><a href="#Press">Press</a></jqx-menu-item>
                <jqx-menu-item><a href="#Investor">Investor Relations</a></jqx-menu-item>
                <jqx-menu-item><a href="#CorporateAffairs">Corporate Affairs</a></jqx-menu-item>
                <jqx-menu-item><a href="#Careers">Careers</a></jqx-menu-item>
                <jqx-menu-item><a href="#Showcase">Showcase</a></jqx-menu-item>
                <jqx-menu-item><a href="#Events">Events</a></jqx-menu-item>
                <jqx-menu-item><a href="#ContactUs">Contact Us</a></jqx-menu-item>
                <jqx-menu-item><a href="#Become an affijqx-menu-itemate">Become an affiliate</a></jqx-menu-item>
            </jqx-menu-items>
        </jqx-menu-item>
    </jqx-menu-items>
</jqx-menu>
```

### Navigation Bar

The ```jqx-navigation-bar``` tag helper adds a NavigationBar component to a web page.

```html
<script src="~/jqwidgets/jqxnavigationbar.js"></script>

@{
    ViewData["Title"] = "ASP .NET MVC NavigationBar Example";
}

<jqx-navigation-bar height="300" width="500" theme="@ViewData["Theme"]">
    <jqx-navigation-bar-panel>
        <jqx-navigation-bar-panel-header>Header 1</jqx-navigation-bar-panel-header>
        <jqx-navigation-bar-panel-body><label style="padding: 15px;">Body 1</label></jqx-navigation-bar-panel-body>
    </jqx-navigation-bar-panel>
    <jqx-navigation-bar-panel>
        <jqx-navigation-bar-panel-header>Header 2</jqx-navigation-bar-panel-header>
        <jqx-navigation-bar-panel-body><label style="padding: 15px;">Body 2</label></jqx-navigation-bar-panel-body>
    </jqx-navigation-bar-panel>
    <jqx-navigation-bar-panel>
        <jqx-navigation-bar-panel-header>Header 3</jqx-navigation-bar-panel-header>
        <jqx-navigation-bar-panel-body><label style="padding: 15px;">Body 3</label></jqx-navigation-bar-panel-body>
    </jqx-navigation-bar-panel>  
</jqx-navigation-bar>

```

### Notification

The ```jqx-notification``` tag helper adds a Notification component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC Notification Example";
}
<label>ASP .NET Core MVC Notification Tag Helper Example</label><br/><br/>
<jqx-button on-click="openMessage()" theme="@ViewData["Theme"]">Open Notification Message</jqx-button>
<jqx-notification id="notification" instance="getNotification()" theme="@ViewData["Theme"]">Notification Message</jqx-notification>
<script>
    var notification = {};
    function getNotification(instance) {
        notification = instance;
    }
    function openMessage() {
        notification.open();
    }
</script>
```

### Number Input

The ```jqx-number-input``` tag helper adds a Number Input component to a web page.

```html
<script src="~/jqwidgets/jqxbuttons.js"></script>
<script src="~/jqwidgets/jqxnumberinput.js"></script>
@{
    ViewData["Title"] = "ASP .NET MVC NumberInput Example";
}
<label>Default Input</label>

<jqx-number-input spin-buttons="true" theme="@ViewData["Theme"]" width="300" height="25" ></jqx-number-input>
<label>Simple Input</label>

<jqx-number-input input-mode="simple" spin-buttons="true" theme="@ViewData["Theme"]" width="300" height="25"></jqx-number-input>

```

### Panel

The ```jqx-panel``` tag helper adds a Panel component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC Panel Example";
}
<label>ASP .NET Core MVC Panel Tag Helper Example</label><br/><br/>
<jqx-panel width=350 height=300 theme="@ViewData["Theme"]">
    <jqx-panel-body>
        <div style='margin: 10px;'>
            <h3>Early History of the Internet</h3>
        </div>
        <!--Content-->
        <div style='white-space: nowrap;'>
            <ul>
                <li>1961 First packet-switching papers</li>
                <li>1966 Merit Network founded</li>
                <li>1966 ARPANET planning starts</li>
                <li>1969 ARPANET carries its first packets</li>
                <li>1970 Mark I network at NPL (UK)</li>
                <li>1970 Network Information Center (NIC)</li>
                <li>1971 Merit Network's packet-switched network operational</li>
                <li>1971 Tymnet packet-switched network</li>
                <li>1972 Internet Assigned Numbers Authority (IANA) established</li>
                <li>1973 CYCLADES network demonstrated</li>
                <li>1974 Telenet packet-switched network</li>
                <li>1976 X.25 protocol approved</li>
                <li>1979 Internet Activities Board (IAB)</li>
                <li>1980 USENET news using UUCP</li>
                <li>1980 Ethernet standard introduced</li>
                <li>1981 BITNET established</li>
            </ul>
        </div>
    </jqx-panel-body>
</jqx-panel>
```

### Password Input

The ```jqx-passwordinput``` tag helper adds a Password Input component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC PasswordInput Example";
}
<label>ASP .NET Core MVC Password Input Tag Helper Example</label><br/><br/>
    <div style='margin-top: 10px;'>
        Password Input
    </div>
    <jqx-password-input width="200" height="25" place-holder="Enter password:" showStrength="true"></jqx-password-input>
```

### Popover

The ```jqx-popover``` tag helper adds a popover components to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@{
    ViewData["Title"] = "ASP .NET MVC Popover Example";
    List<KeyValuePair<string, object>> settings = new List<KeyValuePair<string, object>>()
    {
        new KeyValuePair<string, object>("offset", "{left: -50, top: 0}"),
        new KeyValuePair<string, object>("arrowOffsetValue", 50),
        new KeyValuePair<string, object>("title", "Employees"),
        new KeyValuePair<string, object>("showCloseButton", true),
        new KeyValuePair<string, object>("selector", "button"),
        new KeyValuePair<string, object>("theme", ViewData["Theme"])
    };
}
<label>ASP .NET Core MVC PopOver Tag Helper Example</label><br/><br/>
<div class="jqx-widget-header" style="height: 33px; border-width: 1px; border-style: solid; padding:10px;" id="header">
    <jqx-button style="float: right; margin-right: 10px; padding: 8px 12px; border-radius: 6px;" theme="@ViewData["Theme"]" template="inverse">View Employees</jqx-button>
</div>
<jqx-popover settings="settings">
    <div id="movies">
        <table style="min-width: 150px;"><tbody><tr><td style="width: 55px;" rowspan="2"><img height="50" width="45" src="~/images/nancy.png"></td><td>Nancy Davolio</td></tr><tr><td>Sales Representative</td></tr></tbody></table><table style="min-width: 150px;"><tbody><tr><td style="width: 55px;" rowspan="2"><img height="50" width="45" src="~/images/andrew.png"></td><td>Andrew Fuller</td></tr><tr><td>Vice President, Sales</td></tr></tbody></table><table style="min-width: 150px;"><tbody><tr><td style="width: 55px;" rowspan="2"><img height="50" width="45" src="~/images/janet.png"></td><td>Janet Leverling</td></tr><tr><td>Sales Representative</td></tr></tbody></table><table style="min-width: 150px;"><tbody><tr><td style="width: 55px;" rowspan="2"><img height="50" width="45" src="~/images/margaret.png"></td><td>Margaret Peacock</td></tr><tr><td>Sales Representative</td></tr></tbody></table><table style="min-width: 150px;"><tbody><tr><td style="width: 55px;" rowspan="2"><img height="50" width="45" src="~/images/steven.png"></td><td>Steven Buchanan</td></tr><tr><td>Sales Manager</td></tr></tbody></table><table style="min-width: 150px;"><tbody><tr><td style="width: 55px;" rowspan="2"><img height="50" width="45" src="~/images/michael.png"></td><td>Michael Suyama</td></tr><tr><td>Sales Representative</td></tr></tbody></table><table style="min-width: 150px;"><tbody><tr><td style="width: 55px;" rowspan="2"><img height="50" width="45" src="~/images/robert.png"></td><td>Robert King</td></tr><tr><td>Sales Representative</td></tr></tbody></table><table style="min-width: 150px;"><tbody><tr><td style="width: 55px;" rowspan="2"><img height="50" width="45" src="~/images/laura.png"></td><td>Laura Callahan</td></tr><tr><td>Inside Sales Coordinator</td></tr></tbody></table><table style="min-width: 150px;"><tbody><tr><td style="width: 55px;" rowspan="2"><img height="50" width="45" src="~/images/anne.png"></td><td>Anne Dodsworth</td></tr><tr><td>Sales Representative</td></tr></tbody></table>
    </div>
</jqx-popover>
```

### Progress Bar

The ```jqx-progress-bar``` tag helper adds a Progress Bar component to a web page.

```html
<script src="~/jqwidgets/jqxprogressbar.js"></script>

@using jQWidgets.AspNetCore.Mvc.TagHelpers

@{
    ViewData["Title"] = "ASP .NET MVC ProgressBar Example";
}

<jqx-progress-bar id="toolbar" theme="@ViewData["theme"]" value="50" width="300" height="35"></jqx-progress-bar>
```

### Radio Button

The ```jqx-radio-button``` tag helper adds a Radio Button component to a web page.

```html
<script src="~/jqwidgets/jqxradiobutton.js"></script>

@model jQWidgetsDemosContext
@using jQWidgets.AspNet.Core.Models;
@{
    ViewData["Title"] = "ASP .NET MVC Radio Button Example";
    Contract contract = Model.ContractDuration;
    bool year = false;
    bool halfYear = false;
    bool quarterYear = false;
    bool month = false;
    if (contract == Contract.Year)
    {
        year = true;
    }
    if (contract == Contract.HalfYear)
    {
        halfYear = true;
    }
    if (contract == Contract.QuarterYear)
    {
        quarterYear = true;
    }
    if (contract == Contract.Month)
    {
        month = true;
    }
}

<jqx-radio-button width="200" height="30" theme="@ViewData["Theme"]" on-checked="@Url.Action("Year", "TagHelpers")" checked="year">12 Months Contract</jqx-radio-button>
<jqx-radio-button width="200" height="30" theme="@ViewData["Theme"]" on-checked="@Url.Action("HalfYear", "TagHelpers")" checked="halfYear">6 Months Contract</jqx-radio-button>
<jqx-radio-button width="200" height="30" theme="@ViewData["Theme"]" on-checked="@Url.Action("QuarterYear", "TagHelpers")" checked="quarterYear">3 Months Contract</jqx-radio-button>
<jqx-radio-button width="200" height="30" theme="@ViewData["Theme"]" on-checked="@Url.Action("Month", "TagHelpers")" checked="month">1 Month Contract</jqx-radio-button>
```

### Range Selector

The ```jqx-range-selector``` tag helper adds a Range Selector component to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@{
    ViewData["Title"] = "ASP .NET MVC RangeSelector Example";
    List<KeyValuePair<string, object>> settings = new List<KeyValuePair<string, object>>()
    {
        new KeyValuePair<string, object>("width", 750),
        new KeyValuePair<string, object>("height", 100),
        new KeyValuePair<string, object>("min", 0),
        new KeyValuePair<string, object>("minorTicksInterval", 1),
        new KeyValuePair<string, object>("majorTicksInterval", 10),
        new KeyValuePair<string, object>("max", 200),
        new KeyValuePair<string, object>("range", "{ from: 10, to: 50 }"),
        new KeyValuePair<string, object>("theme", ViewData["Theme"])
    };
}
<label>ASP .NET Core MVC Range Selector Tag Helper Example</label><br/><br/>
<jqx-range-selector settings="settings" ></jqx-range-selector>
```

### Rating

The ```jqx-rating``` tag helper adds a Rating component to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@{
    ViewData["Title"] = "ASP .NET MVC Rating Example";
}
<label>ASP .NET Core MVC Rating Tag Helper Example</label><br/><br/>
<jqx-rating theme="@ViewData["theme"]" value="3" width="200" height="35"></jqx-rating>
```

### Ribbon

The ```jqx-ribbon``` tag helper adds a Ribbon component to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@{
    ViewData["Title"] = "ASP .NET MVC Ribbon Example";
}
<label>ASP .NET Core MVC Ribbon Tag Helper Example</label><br/><br/>
<jqx-ribbon mode="popup" theme="@ViewData["Theme"]" width="850">
    <jqx-tab-panel>
        <jqx-tab-panel-header style="margin-left: 30px;">Node.js</jqx-tab-panel-header>
        <jqx-tab-panel-body> Node.js is an event-driven I/O server-side JavaScript environment based on V8. It
        is intended for writing scalable network programs such as web servers. It was created
        by Ryan Dahl in 2009, and its growth is sponsored by Joyent, which employs Dahl.
        Similar environments written in other programming languages include Twisted for
        Python, Perl Object Environment for Perl, libevent for C and EventMachine for Ruby.
        Unlike most JavaScript, it is not executed in a web browser, but is instead a form
        of server-side JavaScript. Node.js implements some CommonJS specifications. Node.js
        includes a REPL environment for interactive testing.</jqx-tab-panel-body>
    </jqx-tab-panel>
    <jqx-tab-panel>
        <jqx-tab-panel-header>JavaServer Pages</jqx-tab-panel-header>
            <jqx-tab-panel-body>
                JavaServer Pages (JSP) is a Java technology that helps software developers serve
                dynamically generated web pages based on HTML, XML, or other document types. Released
                in 1999 as Sun's answer to ASP and PHP,[citation needed] JSP was designed to address
                the perception that the Java programming environment didn't provide developers with
                enough support for the Web. To deploy and run, a compatible web server with servlet
                container is required. The Java Servlet and the JavaServer Pages (JSP) specifications
                from Sun Microsystems and the JCP (Java Community Process) must both be met by the
                container.
            </jqx-tab-panel-body>
    </jqx-tab-panel>
    <jqx-tab-panel>
        <jqx-tab-panel-header>Active Server Pages</jqx-tab-panel-header>
        <jqx-tab-panel-body> ASP.NET is a web application framework developed and marketed by Microsoft to allow
            programmers to build dynamic web sites, web applications and web services. It was
            first released in January 2002 with version 1.0 of the .NET Framework, and is the
            successor to Microsoft's Active Server Pages (ASP) technology. ASP.NET is built
            on the Common Language Runtime (CLR), allowing programmers to write ASP.NET code
            using any supported .NET language. The ASP.NET SOAP extension framework allows ASP.NET
            components to process SOAP messages.</jqx-tab-panel-body>
    </jqx-tab-panel>
    <jqx-tab-panel>
        <jqx-tab-panel-header>Python</jqx-tab-panel-header>
        <jqx-tab-panel-body> Python is a general-purpose, high-level programming language[5] whose design philosophy
            emphasizes code readability. Python claims to "[combine] remarkable power with very
            clear syntax",[7] and its standard library is large and comprehensive. Its use of
            indentation for block delimiters is unique among popular programming languages.
            Python supports multiple programming paradigms, primarily but not limited to object-oriented,
            imperative and, to a lesser extent, functional programming styles. It features a
            fully dynamic type system and automatic memory management, similar to that of Scheme,
            Ruby, Perl, and Tcl. Like other dynamic languages, Python is often used as a scripting
            language, but is also used in a wide range of non-scripting contexts.</jqx-tab-panel-body>
    </jqx-tab-panel>
    <jqx-tab-panel>
        <jqx-tab-panel-header>Perl</jqx-tab-panel-header>
        <jqx-tab-panel-body> Perl is a high-level, general-purpose, interpreted, dynamic programming language.
            Perl was originally developed by Larry Wall in 1987 as a general-purpose Unix scripting
            language to make report processing easier. Since then, it has undergone many changes
            and revisions and become widely popular amongst programmers. Larry Wall continues
            to oversee development of the core language, and its upcoming version, Perl 6. Perl
            borrows features from other programming languages including C, shell scripting (sh),
            AWK, and sed.[5] The language provides powerful text processing facilities without
            the arbitrary data length limits of many contemporary Unix tools, facilitating easy
            manipulation of text files.</jqx-tab-panel-body>
    </jqx-tab-panel>
</jqx-ribbon>
```

### Scheduler

The ```jqx-scheduler``` tag helper adds a Scheduler component to a web page.

```
create - {{String}} which determines the URL called when a Scheduler appointment is added.
delete - {{String}} which determines the URL called when a Scheduler appointment is deleted.
edit - {{String}} which determines the URL called when a Scheduler appointment is updated.
instance - {{String}} which determines the javascript member within the Script tag which refers to the Input's instance. This member is useful when you want to dynamically invoke API members of the Javascript component.
source-id - {{String}} which determines the data source's ID member.
source-id-for - {{ModelExpression}} used for model binding and determines the data source's ID member.
source-root - {{String}} which determines the data source's Root member.
source-total-records - {{Integer}} which determines the data source's TotalRecords member.
source-url - {{String}} which determines the data source's URL.
source-model - {{Model}} which determines the data source's Model.
```

```jqx-scheduler-views``` tag helper defines the Scheduler's views collection. <br />
```jqx-scheduler-view``` tag helper defines a Scheduler view. <br />
```jqx-scheduler-time-ruler``` tag helper defines the Scheduler's time ruler.

### ScrollBar

The ```jqx-scrollbar``` tag helper adds a ScrollBar component to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@{
    ViewData["Title"] = "ASP .NET MVC ScrollBar Example";
    List<KeyValuePair<string, object>> settings = new List<KeyValuePair<string, object>>()
    {
        new KeyValuePair<string, object>("width", 450),
        new KeyValuePair<string, object>("height", 18),
        new KeyValuePair<string, object>("min", 0),
        new KeyValuePair<string, object>("max", 10000),
        new KeyValuePair<string, object>("theme", ViewData["Theme"])
    };
}
<script>
    function valueChanged(event) {
        $("#log").html("Horizontal (" + parseInt(event.currentValue) + ")");
    }
</script>
<label>ASP .NET Core MVC ScrollBar Tag Helper Example</label><br/><br/>
<jqx-scrollbar on-valueChanged="valueChanged()" settings="settings" ></jqx-scrollbar>
<br /><br />
<div id="log"></div>
```

### ScrollView

The ```jqx-scrollview``` tag helper adds a ScrollView component to a web page.

```html
@model IEnumerable<jQWidgets.AspNet.Core.Models.SalesEmployee>
@{
    ViewData["Title"] = "ASP .NET MVC ScrollView Example";
}
<style type="text/css">
    .photo {
        width: 600px;
        height: 450px;
        background-color: #000;
        background-position: center;
        background-repeat: no-repeat;
    }
</style>
<label>ASP .NET Core MVC ScrollView Tag Helper Example</label><br/><br/>
<jqx-scrollview theme="@ViewData["Theme"]" width="600" height="450" id="photoGallery">
    <div><div class="photo" style="background-image: url(/images/imageNature1.jpg)"></div></div>
    <div><div class="photo" style="background-image: url(/images/imageNature2.jpg)"></div></div>
    <div><div class="photo" style="background-image: url(/images/imageNature3.jpg)"></div></div>
    <div><div class="photo" style="background-image: url(/images/imageNature4.jpg)"></div></div>
    <div><div class="photo" style="background-image: url(/images/imageNature5.jpg)"></div></div>
</jqx-scrollview>
```

### Slider

The ```jqx-slider``` tag helper adds a Bullet Chart component to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@{
    ViewData["Title"] = "ASP .NET MVC Slider Example";
}
<label>ASP .NET Core MVC Slider Tag Helper Example</label><br/><br/>
<jqx-slider theme="@ViewData["Theme"]" width="350" height="50" ></jqx-slider>
```

### Splitter

The ```jqx-splitter``` tag helper adds a Bullet Chart component to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@{
    ViewData["Title"] = "ASP .NET MVC Splitter Example";
}
<label>ASP .NET Core MVC Splitter Tag Helper Example</label><br/><br/>
<jqx-splitter theme="@ViewData["theme"]" width="800" height="400">
    <jqx-splitter-panel>
        <jqx-tabs theme="@ViewData["theme"]" style="border:none;" width="100%" height="100%">
            <jqx-tab-panel>
                <jqx-tab-panel-header style="margin-left:30px;">Tab 1</jqx-tab-panel-header>
                <jqx-tab-panel-body>Content 1</jqx-tab-panel-body>
            </jqx-tab-panel>
            <jqx-tab-panel>
                <jqx-tab-panel-header>Tab 2</jqx-tab-panel-header>
                <jqx-tab-panel-body>Content 2</jqx-tab-panel-body>
            </jqx-tab-panel>
        </jqx-tabs>
    </jqx-splitter-panel>
    <jqx-splitter-panel>
        <jqx-tree style="border:none;" height="100%" width="100%">
            <jqx-tree-items>
                <jqx-tree-item>Item 1</jqx-tree-item>
                <jqx-tree-item>Item 2</jqx-tree-item>
                <jqx-tree-item>Item 3
                    <jqx-tree-items>
                        <jqx-tree-item>Sub Item 3.1</jqx-tree-item>
                        <jqx-tree-item>Sub Item 3.2</jqx-tree-item>
                        <jqx-tree-item>Sub Item 3.3</jqx-tree-item>
            </jqx-tree-items>
                </jqx-tree-item>
                <jqx-tree-item>Item 4</jqx-tree-item>
                <jqx-tree-item>Item 5</jqx-tree-item>
     </jqx-tree-items>
        </jqx-tree>
    </jqx-splitter-panel>
</jqx-splitter>
```

```jqx-splitter-panel``` tag helper defines a splitter panel. 
The Splitter component should have exactly two such tag helpers within the main ```jqx-splitter``` tag helper.

### Switch Button

The ```jqx-switch-button``` tag helper adds a Switch Button component to a web page.

```html
@{
    ViewData["Title"] = "ASP .NET MVC Switch Button Example";
}
<label>ASP .NET Core MVC SwitchButton Tag Helper Example</label><br/><br/>
<jqx-switch-button theme="@ViewData["Theme"]" width="150" height="30"></jqx-switch-button>
```

### Tabs

The ```jqx-tabs``` tag helper adds a Tabs component to a web page. <br />
```jqx-tab-panel``` tag helper defines a Tab's panel. <br />
```jqx-tab-panel-header``` tag helper defines a panel's header. <br />
```jqx-tab-panel-body``` tag helper defines a panel's body.

```html
<script src="~/jqwidgets/jqxtabs.js"></script>


@using jQWidgets.AspNetCore.Mvc.TagHelpers

@{
    ViewData["Title"] = "ASP .NET MVC Tabs Example";
}

<script>
 
</script>
<jqx-tabs theme="@ViewData["Theme"]" width="850">
    <jqx-tab-panel>
        <jqx-tab-panel-header style="margin-left: 30px;">Node.js</jqx-tab-panel-header>
        <jqx-tab-panel-body> Node.js is an event-driven I/O server-side JavaScript environment based on V8. It
        is intended for writing scalable network programs such as web servers. It was created
        by Ryan Dahl in 2009, and its growth is sponsored by Joyent, which employs Dahl.
        Similar environments written in other programming languages include Twisted for
        Python, Perl Object Environment for Perl, libevent for C and EventMachine for Ruby.
        Unlike most JavaScript, it is not executed in a web browser, but is instead a form
        of server-side JavaScript. Node.js implements some CommonJS specifications. Node.js
        includes a REPL environment for interactive testing.</jqx-tab-panel-body>
    </jqx-tab-panel>
    <jqx-tab-panel>
        <jqx-tab-panel-header>JavaServer Pages</jqx-tab-panel-header>
            <jqx-tab-panel-body>
                JavaServer Pages (JSP) is a Java technology that helps software developers serve
                dynamically generated web pages based on HTML, XML, or other document types. Released
                in 1999 as Sun's answer to ASP and PHP,[citation needed] JSP was designed to address
                the perception that the Java programming environment didn't provide developers with
                enough support for the Web. To deploy and run, a compatible web server with servlet
                container is required. The Java Servlet and the JavaServer Pages (JSP) specifications
                from Sun Microsystems and the JCP (Java Community Process) must both be met by the
                container.
            </jqx-tab-panel-body>
    </jqx-tab-panel>
    <jqx-tab-panel>
        <jqx-tab-panel-header>Active Server Pages</jqx-tab-panel-header>
        <jqx-tab-panel-body> ASP.NET is a web application framework developed and marketed by Microsoft to allow
            programmers to build dynamic web sites, web applications and web services. It was
            first released in January 2002 with version 1.0 of the .NET Framework, and is the
            successor to Microsoft's Active Server Pages (ASP) technology. ASP.NET is built
            on the Common Language Runtime (CLR), allowing programmers to write ASP.NET code
            using any supported .NET language. The ASP.NET SOAP extension framework allows ASP.NET
            components to process SOAP messages.</jqx-tab-panel-body>
    </jqx-tab-panel>
    <jqx-tab-panel>
        <jqx-tab-panel-header>Python</jqx-tab-panel-header>
        <jqx-tab-panel-body> Python is a general-purpose, high-level programming language[5] whose design philosophy
            emphasizes code readability. Python claims to "[combine] remarkable power with very
            clear syntax",[7] and its standard library is large and comprehensive. Its use of
            indentation for block delimiters is unique among popular programming languages.
            Python supports multiple programming paradigms, primarily but not limited to object-oriented,
            imperative and, to a lesser extent, functional programming styles. It features a
            fully dynamic type system and automatic memory management, similar to that of Scheme,
            Ruby, Perl, and Tcl. Like other dynamic languages, Python is often used as a scripting
            language, but is also used in a wide range of non-scripting contexts.</jqx-tab-panel-body>
    </jqx-tab-panel>
    <jqx-tab-panel>
        <jqx-tab-panel-header>Perl</jqx-tab-panel-header>
        <jqx-tab-panel-body> Perl is a high-level, general-purpose, interpreted, dynamic programming language.
            Perl was originally developed by Larry Wall in 1987 as a general-purpose Unix scripting
            language to make report processing easier. Since then, it has undergone many changes
            and revisions and become widely popular amongst programmers. Larry Wall continues
            to oversee development of the core language, and its upcoming version, Perl 6. Perl
            borrows features from other programming languages including C, shell scripting (sh),
            AWK, and sed.[5] The language provides powerful text processing facilities without
            the arbitrary data length limits of many contemporary Unix tools, facilitating easy
            manipulation of text files.</jqx-tab-panel-body>
    </jqx-tab-panel>
</jqx-tabs>

```

### TextArea

The ```jqx-textarea``` tag helper adds a Text Area component to a web page.

```html
<script src="~/jqwidgets/jqxbuttons.js"></script>
<script src="~/jqwidgets/jqxscrollbar.js"></script>
<script src="~/jqwidgets/jqxtextarea.js"></script>


@model IEnumerable<jQWidgets.AspNet.Core.Models.SalesEmployee>

@{
    ViewData["Title"] = "ASP .NET MVC TextArea Example";
}
<script>
    function change(event) {
        var args = event.args;
        document.getElementById("log").innerHTML = "Label: " + args.label + ", Value: " + args.value;;
    }
</script>
<label>Enter Name:</label>
<jqx-text-area on-change="change()" display-member="Name" selected-index="0" value-member="ID" theme="@ViewData["Theme"]" width="250" height="100" source="Model"></jqx-text-area>
(ex: An)
<br /><br />
<div id="log"></div>
```

### Toolbar

The ```jqx-tool-bar``` tag helper adds a Toolbar component to a web page.

```html
<script src="~/jqwidgets/jqxbuttons.js"></script>
<script src="~/jqwidgets/jqxscrollbar.js"></script>
<script src="~/jqwidgets/jqxlistbox.js"></script>
<script src="~/jqwidgets/jqxinput.js"></script>
<script src="~/jqwidgets/jqxdropdownlist.js"></script>
<script src="~/jqwidgets/jqxcombobox.js"></script>
<script src="~/jqwidgets/jqxtoolbar.js"></script>


@using jQWidgets.AspNetCore.Mvc.TagHelpers

@{
    ViewData["Title"] = "ASP .NET MVC Toolbar Example";
}
<style type="text/css">
    .buttonIcon {
        margin: -5px 0 0 -3px;
        width: 16px;
        height: 17px;
    }
</style>

<script>
    function initTools (type, index, tool, menuToolIninitialization) {
        var theme = $("#toolbar").jqxToolBar("theme");

        if (type == "toggleButton") {
            var icon = $("<div class='jqx-editor-toolbar-icon jqx-editor-toolbar-icon-" + theme + " buttonIcon'></div>");
        }
        switch (index) {
            case 0:
                icon.addClass("jqx-editor-toolbar-icon-bold jqx-editor-toolbar-icon-bold-" + theme);
                icon.attr("title", "Bold");
                tool.append(icon);
                break;
            case 1:
                icon.addClass("jqx-editor-toolbar-icon-italic jqx-editor-toolbar-icon-italic-" + theme);
                icon.attr("title", "Italic");
                tool.append(icon);
                break;
            case 2:
                icon.addClass("jqx-editor-toolbar-icon-underline jqx-editor-toolbar-icon-underline-" + theme);
                icon.attr("title", "Underline");
                tool.append(icon);
                break;
            case 3:
                tool.jqxToggleButton({ width: 80, toggled: true });
                tool.text("Enabled");
                tool.on("click", function () {
                    var toggled = tool.jqxToggleButton("toggled");
                    if (toggled) {
                        tool.text("Enabled");
                    } else {
                        tool.text("Disabled");
                    }
                });
                break;
            case 4:
                tool.jqxDropDownList({ width: 130, source: ["<span style='font-family: Courier New;'>Courier New</span>", "<span style='font-family: Times New Roman;'>Times New Roman</span>", "<span style='font-family: Verdana;'>Verdana</span>"], selectedIndex: 1 });
                break;
            case 5:
                tool.jqxComboBox({ width: 50, source: [8, 9, 10, 11, 12, 14, 16, 18, 20], selectedIndex: 3 });
                break;
            case 6:
                tool.jqxInput({ width: 200, placeHolder: "Type here to search..." });
                break;
            case 7:
                var button = $("<div>" + "<img src='../../images/administrator.png' title='Custom tool' />" + "</div>");
                tool.append(button);
                button.jqxButton({ height: 15 });
                break;
        }
    }
</script>
<jqx-tool-bar id="toolbar" theme="@ViewData["theme"]" initTools="initTools()" tools="toggleButton toggleButton toggleButton | toggleButton | dropdownlist combobox | input | custom" width="800" height="35"></jqx-tool-bar>

```

### Tooltip

The ```jqx-tool-tip``` tag helper adds a Tooltip component to a web page.

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@{
    ViewData["Title"] = "ASP .NET MVC Tooltip Example";
    List<KeyValuePair<string, object>> settings = new List<KeyValuePair<string, object>>()
    {
        new KeyValuePair<string, object>("position", "mouse"),
        new KeyValuePair<string, object>("content", "Tooltip"),
        new KeyValuePair<string, object>("selector", "tooltip"),
        new KeyValuePair<string, object>("theme", ViewData["Theme"])
    };
}
<label>ASP .NET Core MVC Tooltip Tag Helper Example</label><br/><br/>
<span id="tooltip">Move cursor here to see the tooltip</span>
<jqx-tool-tip settings="settings"></jqx-tool-tip>
```

### Tree

The ```jqx-tree``` tag helper adds a Tree component to a web page.

```
@model IEnumerable<jQWidgets.AspNet.Core.Models.TreeItem>
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@{
    ViewData["Title"] = "ASP .NET MVC Tree Example";
}
<label>ASP .NET Core MVC Tree Tag Helper Example</label><br/><br/>
<jqx-tree theme="@ViewData["Theme"]" id="solutionExplorerTree" width="200" items-member="Items" display-member="Label" source="Model"></jqx-tree>
```

### TreeGrid

The TreeGrid tag helper shares the same API members as the Javascript DataTable widget i.e all properties, methods and events can be used. 
Additional properties for the ```jqx-datatable``` tag helper are:

```
create - {{String}} which determines the URL called when a TreeGrid row is added.
datafield-for - {{ModelExpression}} used for model binding and determines the column's bound member.
delete - {{String}} which determines the URL called when a TreeGrid row is deleted.
edit - {{String}} which determines the URL called when the TreeGrid is edited.
instance - {{String}} which determines the javascript member within the Script tag which refers to the TreeGrid's instance. This member is useful when you want to dynamically invoke API members of the Javascript component.
server-processing - {{Boolean}} which determines whether server processing is enabled.
source-id - {{String}} which determines the data source's ID member.
source-id-for - {{ModelExpression}} used for model binding and determines the data source's ID member.
source-root - {{String}} which determines the data source's Root member.
source-total-records - {{Integer}} which determines the data source's TotalRecords member.
source-url - {{String}} which determines the data source's URL.
source-model - {{Model}} which determines the data source's Model.
```

```jqx-treegrid-columns``` tag helper should be defined within the ```jqx-treegrid``` tag helper and defines the TreeGrid columns collection. <br />
```jqx-treegrid-column``` tag helper should be defined within the ```jqx-treegrid-columns``` tag helper and defines a TreeGrid column. <br />
```jqx-treegrid-column-groups``` tag helper should be defined within the ```jqx-treegrid``` tag helper and defines the TreeGrid columns hierarchy. <br />
```jqx-treegrid-column-group``` tag helper should be defined within the ```jqx-treegrid-column-groups``` tag helper and defines a TreeGrid column group.

```html
<script src="~/jqwidgets/jqxbuttons.js"></script>
<script src="~/jqwidgets/jqxscrollbar.js"></script>
<script src="~/jqwidgets/jqxlistbox.js"></script>
<script src="~/jqwidgets/jqxdropdownlist.js"></script>
<script src="~/jqwidgets/jqxdatatable.js"></script>
<script src="~/jqwidgets/jqxtreegrid.js"></script>
@model IEnumerable<jQWidgets.AspNet.Core.Models.Employee>

@{
    ViewData["Title"] = "ASP .NET MVC TreeGrid Example";
}
@{
    var employee = Model.FirstOrDefault();
}
<script>
    var treeGridInstance;
    function getInstance(instance)
    {
        treeGridInstance = instance;
    }
    function treeGridReady()
    {
        treeGridInstance.expandRow(2);
    }
</script>
<jqx-tree-grid key-datafield-for="@(employee.EmployeeID)" ready="treeGridReady()" source-id-for="@(employee.EmployeeID)" instance="getInstance()" parent-datafield-for="@(employee.ManagerID)" theme="@ViewData["Theme"]" sortable="true" width="850" source="Model"> 
    <jqx-tree-grid-columns>
        <jqx-tree-grid-column dataField-for="@(employee.FirstName)" width="100" text="First Name"></jqx-tree-grid-column>
        <jqx-tree-grid-column datafield-for="@(employee.LastName)" width="100" text="Last Name"></jqx-tree-grid-column>
        <jqx-tree-grid-column datafield-for="@(employee.Title)" width="150"></jqx-tree-grid-column>
        <jqx-tree-grid-column datafield-for="@(employee.Address)" width="200"></jqx-tree-grid-column>
        <jqx-tree-grid-column datafield-for="@(employee.City)" width="150"></jqx-tree-grid-column>
        <jqx-tree-grid-column datafield-for="@(employee.Country)"></jqx-tree-grid-column>
    </jqx-tree-grid-columns>
</jqx-tree-grid>


```

### TreeMap

The ```jqx-treemap``` tag helper adds a TreeMap component to a web page.

```html
<script src="~/jqwidgets/jqxtreemap.js"></script>

@model IEnumerable<jQWidgets.AspNet.Core.Models.Employee>

@{
    ViewData["Title"] = "ASP .NET MVC TreeMap Example";
}
@{
    var employee = Model.FirstOrDefault();
}
<jqx-tree-map display-member="FirstName" value-member="EmployeeID" theme="@ViewData["Theme"]" width="850" source="Model"></jqx-tree-map>


```

### Validator

The ```jqx-validator``` tag helper adds a Validator Chart component to a web page.

```html
<script src="~/jqwidgets/jqxvalidator.js"></script>
<script src="~/jqwidgets/jqxbuttons.js"></script>
<script src="~/jqwidgets/jqxcheckbox.js"></script>
<script src="~/jqwidgets/jqxinput.js"></script>
<script src="~/jqwidgets/jqxpasswordinput.js"></script>

@using jQWidgets.AspNetCore.Mvc.TagHelpers

@{
    ViewData["Title"] = "ASP .NET MVC Validator Example";

    List<KeyValuePair<string, object>> settings = new List<KeyValuePair<string, object>>()
    {
           new KeyValuePair<string, object>("rules", new List<ValidatorRule>()
            {
                new ValidatorRule() { Input ="#username", Action="keyup, blur", Rule="required" },
                new ValidatorRule() { Input ="#password", Action="keyup, blur", Rule="required" }
            }
        ),
        new KeyValuePair<string, object>("selector", "form"),
        new KeyValuePair<string, object>("theme", ViewData["Theme"])
    };
}
<script>
    var validator;
    function getValidator(instance) {
        validator = instance;
    }
    function validate() {
        validator.validate();
    }
</script>
<jqx-validator hint-type="label" instance="getValidator()" settings="settings"></jqx-validator>
<form class="form" id="form" target="form-iframe" method="post" action="login.php" style="width: 650px;">
    <div>
        <h2>Login Demo</h2>
    </div>
    <label style="margin-top:10px;">Username:</label>
    <div style="margin-top:10px;">
        <jqx-input height="25" theme="@ViewData["theme"]" type="text" id="username" name="username"></jqx-input>
    </div>
    <label>Password:</label>
    <div style="margin-top:10px;">
        <jqx-password-input height="25" theme="@ViewData["theme"]" type="password" id="password" name="password"></jqx-password-input>
    </div>
    <div style="margin-top:10px;">
        <jqx-check-box theme="@ViewData["theme"]" name="rememberme" id="rememberme">Keep me logged in on this computer</jqx-check-box>
    </div>
    <div style="margin-top:10px;">
        <jqx-button theme="@ViewData["theme"]" on-click="validate()" id="loginButton" type="submit" value="Login"></jqx-button>
    </div>
</form>
```

### Window

The ```jqx-window``` tag helper adds a Window Chart component to a web page.

```html
<script src="~/jqwidgets/jqxwindow.js"></script>
<script src="~/jqwidgets/jqxtabs.js"></script>

@model IEnumerable<jQWidgets.AspNet.Core.Models.SalesEmployee>

@{
    ViewData["Title"] = "ASP .NET MVC Window Example";
}
<jqx-window theme="@ViewData["Theme"]" width="500" height="250">
    <jqx-window-header>Info</jqx-window-header>
    <jqx-window-body>
        <jqx-tabs theme="@ViewData["Theme"]" style="margin:-1px;" width="100%" height="100%">
            <jqx-tab-panel>
                <jqx-tab-panel-header style="margin-left:30px;">CISC</jqx-tab-panel-header>
                <jqx-tab-panel-body>
                    <div style="padding: 10px;">
                        Before the RISC philosophy became prominent, many computer architects tried to bridge
                        the so called semantic gap, i.e. to design instruction sets that directly supported
                        high-level programming constructs such as procedure calls, loop control, and complex
                        addressing modes, allowing data structure and array accesses to be combined into
                        single instructions. Instructions are also typically highly encoded in order to
                        further enhance the code density...
                    </div>
                </jqx-tab-panel-body>
            </jqx-tab-panel>
            <jqx-tab-panel>
                <jqx-tab-panel-header>RISC</jqx-tab-panel-header>
                <jqx-tab-panel-body>
                    <div style="padding: 10px;">
                        Some aspects attributed to the first RISC-labeled designs around 1975 include the
                        observations that the memory-restricted compilers of the time were often unable
                        to take advantage of features intended to facilitate manual assembly coding, and
                        that complex addressing modes take many cycles to perform due to the required additional
                        memory accesses...
                    </div>
                </jqx-tab-panel-body>
            </jqx-tab-panel>
            <jqx-tab-panel>
                <jqx-tab-panel-header>Database management system</jqx-tab-panel-header>
                <jqx-tab-panel-body>
                    <div style="padding: 10px;">
                        A database management system (DBMS) is a software package with computer programs
                        that control the creation, maintenance, and the use of a database. It allows organizations
                        to conveniently develop databases for various applications by database administrators
                        (DBAs) and other specialists. A database is an integrated collection of data records,
                        files, and other database objects...
                    </div>
                </jqx-tab-panel-body>
            </jqx-tab-panel>
        </jqx-tabs>
    </jqx-window-body>
</jqx-window>

```

```jqx-window-body``` tag helper defines the window's body. <br />
```jqx-window-header``` tag helper defines the window's header.
