# nopCommerce-Guide
A Guideline to built your own NopCommerce Themes

##Javascript Dependencies


**Javascript dependencies**
All javascript files for the presentation layer live in the following folder:

```sh
ProjectName\Presentation\Nop.Web\scripts\
```

**Adding Javascript files**

To add javascript files into your NopCommerce platform you should add it to the following file.

**Example: 1.0**

```sh
ProjectName\Presentation\Nop.Web\Views\Shared\_Root.Head.cshtml

@{
    var displayMiniProfiler = EngineContext.Current.Resolve<Nop.Core.Domain.StoreInformationSettings>().DisplayMiniProfilerInPublicStore;

    //resources
    Html.AppendCssFileParts("~/Content/jquery-ui-themes/smoothness/jquery-ui-1.10.3.custom.min.css");


    Html.AppendScriptParts("~/Scripts/bootstrap.min.js"); // <-------
    Html.AppendScriptParts("~/Scripts/public.ajaxcart.js");
    Html.AppendScriptParts("~/Scripts/public.common.js");
    Html.AppendScriptParts("~/Scripts/jquery-migrate-1.2.1.min.js");
    Html.AppendScriptParts("~/Scripts/jquery-ui-1.10.3.custom.min.js");
    Html.AppendScriptParts("~/Scripts/jquery.validate.unobtrusive.min.js");
    Html.AppendScriptParts("~/Scripts/jquery.validate.min.js");
    Html.AppendScriptParts("~/Scripts/jquery-1.10.2.min.js");


    //X-UA-Compatible tag
    var commonSettings = EngineContext.Current.Resolve<CommonSettings>();
    if (commonSettings.RenderXuaCompatible)
    {
        Html.AppendHeadCustomParts(string.Format("<meta http-equiv=\"X-UA-Compatible\" content=\"{0}\"/>", commonSettings.XuaCompatibleValue));
    }
}
```

*The example above (1.0) Shows how to add* **bootstrap's** *javascript file to the NopCommerce platform.*


