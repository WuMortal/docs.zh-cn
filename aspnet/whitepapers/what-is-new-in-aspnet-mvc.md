---
uid: whitepapers/what-is-new-in-aspnet-mvc
title: "什么是 ASP.NET MVC 2 中的新增功能 |Microsoft 文档"
author: rick-anderson
description: "本文档介绍了新增功能和 ASP.NET MVC 2 中引入的改进。 本文档还是可供下载的。"
ms.author: aspnetcontent
manager: wpickett
ms.date: 04/20/2010
ms.topic: article
ms.assetid: 69a8d6f8-4b10-4602-8822-2d6c05fc432b
ms.technology: 
ms.prod: .net-framework
msc.legacyurl: /whitepapers/what-is-new-in-aspnet-mvc
msc.type: content
ms.openlocfilehash: e7f92dd7a09d1986ad775203effcbce76fb0e6f4
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2017
---
<a name="whats-new-in-aspnet-mvc-2"></a><span data-ttu-id="d2e96-104">什么是 ASP.NET MVC 2 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="d2e96-104">What’s New in ASP.NET MVC 2</span></span>
====================
> <span data-ttu-id="d2e96-105">本文档介绍了新增功能和 ASP.NET MVC 2 中引入的改进。</span><span class="sxs-lookup"><span data-stu-id="d2e96-105">This document describes new features and improvements introduced in ASP.NET MVC 2.</span></span> <span data-ttu-id="d2e96-106">本文档还为提供[下载](https://download.microsoft.com/download/F/1/6/F16F9AF9-8EF4-4845-BC97-639791D5699C/WhatIsNewInMVC_2.pdf)</span><span class="sxs-lookup"><span data-stu-id="d2e96-106">This document is also available for [Download](https://download.microsoft.com/download/F/1/6/F16F9AF9-8EF4-4845-BC97-639791D5699C/WhatIsNewInMVC_2.pdf)</span></span>


<span data-ttu-id="d2e96-107">[简介](#_TOC1) </span><span class="sxs-lookup"><span data-stu-id="d2e96-107">[Introduction](#_TOC1) </span></span>  
<span data-ttu-id="d2e96-108">[升级到 ASP.NET MVC 2 的 ASP.NET MVC 1.0 项目](#_TOC2) </span><span class="sxs-lookup"><span data-stu-id="d2e96-108">[Upgrading an ASP.NET MVC 1.0 Project to ASP.NET MVC 2](#_TOC2) </span></span>  
<span data-ttu-id="d2e96-109">[新功能](#_TOC3) </span><span class="sxs-lookup"><span data-stu-id="d2e96-109">[New Features](#_TOC3) </span></span>  
<span data-ttu-id="d2e96-110">[模板化帮助器](#_TOC3_1) </span><span class="sxs-lookup"><span data-stu-id="d2e96-110">[Templated Helpers](#_TOC3_1) </span></span>  
<span data-ttu-id="d2e96-111">[区域](#_TOC3_2) </span><span class="sxs-lookup"><span data-stu-id="d2e96-111">[Areas](#_TOC3_2) </span></span>  
<span data-ttu-id="d2e96-112">[对异步控制器的支持](#_TOC3_3) </span><span class="sxs-lookup"><span data-stu-id="d2e96-112">[Support for Asynchronous Controllers](#_TOC3_3) </span></span>  
<span data-ttu-id="d2e96-113">[DefaultValueAttribute 操作方法参数中的支持](#_TOC3_4) </span><span class="sxs-lookup"><span data-stu-id="d2e96-113">[Support for DefaultValueAttribute in Action-Method Parameters](#_TOC3_4) </span></span>  
<span data-ttu-id="d2e96-114">[对绑定的二进制数据，模型联编程序的支持](#_TOC3_5) </span><span class="sxs-lookup"><span data-stu-id="d2e96-114">[Support for Binding Binary Data with Model Binders](#_TOC3_5) </span></span>  
<span data-ttu-id="d2e96-115">[ModelMetadata 和 ModelMetadataProvider 类](#_TOC3_6) </span><span class="sxs-lookup"><span data-stu-id="d2e96-115">[ModelMetadata and ModelMetadataProvider Classes](#_TOC3_6) </span></span>  
<span data-ttu-id="d2e96-116">[对 DataAnnotations 特性的支持](#_TOC3_7) </span><span class="sxs-lookup"><span data-stu-id="d2e96-116">[Support for DataAnnotations Attributes](#_TOC3_7) </span></span>  
<span data-ttu-id="d2e96-117">[模型验证程序提供程序](#_TOC3_8) </span><span class="sxs-lookup"><span data-stu-id="d2e96-117">[Model-Validator Providers](#_TOC3_8) </span></span>  
<span data-ttu-id="d2e96-118">[客户端验证](#_TOC3_9) </span><span class="sxs-lookup"><span data-stu-id="d2e96-118">[Client-Side Validation](#_TOC3_9) </span></span>  
<span data-ttu-id="d2e96-119">[Visual Studio 2010 的新代码段](#_TOC3_10) </span><span class="sxs-lookup"><span data-stu-id="d2e96-119">[New Code Snippets for Visual Studio 2010](#_TOC3_10) </span></span>  
<span data-ttu-id="d2e96-120">[新 RequireHttpsAttribute 操作筛选器](#_TOC3_11) </span><span class="sxs-lookup"><span data-stu-id="d2e96-120">[New RequireHttpsAttribute Action Filter](#_TOC3_11) </span></span>  
<span data-ttu-id="d2e96-121">[重写的 HTTP 方法谓词](#_TOC3_12) </span><span class="sxs-lookup"><span data-stu-id="d2e96-121">[Overriding the HTTP Method Verb](#_TOC3_12) </span></span>  
<span data-ttu-id="d2e96-122">[模板化帮助器的新 HiddenInputAttribute 类](#_TOC3_13) </span><span class="sxs-lookup"><span data-stu-id="d2e96-122">[New HiddenInputAttribute Class for Templated Helpers](#_TOC3_13) </span></span>  
<span data-ttu-id="d2e96-123">[Html.ValidationSummary 帮助器方法可以显示模型级别错误](#_TOC3_14) </span><span class="sxs-lookup"><span data-stu-id="d2e96-123">[Html.ValidationSummary Helper Method Can Display Model-Level Errors](#_TOC3_14) </span></span>  
<span data-ttu-id="d2e96-124">[在 Visual Studio 生成的代码是特定的 T4 模板到.NET framework 目标版本](#_TOC3_15)[API 改进](#_TOC4)</span><span class="sxs-lookup"><span data-stu-id="d2e96-124">[T4 Templates in Visual Studio Generate Code that is Specific to the Target Version of the .NET Framework](#_TOC3_15)[API Improvements](#_TOC4)</span></span>  
[<span data-ttu-id="d2e96-125">重大更改</span><span class="sxs-lookup"><span data-stu-id="d2e96-125">Breaking Changes</span></span>](#_TOC5)  
[<span data-ttu-id="d2e96-126">免责声明</span><span class="sxs-lookup"><span data-stu-id="d2e96-126">Disclaimer</span></span>](#_TOC6)  

## <a id="_TOC1"></a><span data-ttu-id="d2e96-127">简介</span><span class="sxs-lookup"><span data-stu-id="d2e96-127">Introduction</span></span>

<span data-ttu-id="d2e96-128">ASP.NET MVC 2 基于 ASP.NET MVC 1.0，并引入了大量的增强功能和侧重于提高工作效率的功能。</span><span class="sxs-lookup"><span data-stu-id="d2e96-128">ASP.NET MVC 2 builds on ASP.NET MVC 1.0 and introduces a large set of enhancements and features that are focused on increasing productivity.</span></span> <span data-ttu-id="d2e96-129">此版本是与 ASP.NET MVC 1.0 兼容，因此所有知识、 技能、 代码和扩展 ASP.NET MVC 1.0 都继续应用。</span><span class="sxs-lookup"><span data-stu-id="d2e96-129">This release is compatible with ASP.NET MVC 1.0, so all your knowledge, skills, code, and extensions for ASP.NET MVC 1.0 continue to apply.</span></span>

<span data-ttu-id="d2e96-130">有关 ASP.NET MVC 的详细信息，请访问以下资源：</span><span class="sxs-lookup"><span data-stu-id="d2e96-130">For more information about ASP.NET MVC, visit the following resources:</span></span>

- [<span data-ttu-id="d2e96-131">MSDN 上的 ASP.NET MVC 文档</span><span class="sxs-lookup"><span data-stu-id="d2e96-131">ASP.NET MVC documentation on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=159758)
- [<span data-ttu-id="d2e96-132">ASP.NET MVC 网站</span><span class="sxs-lookup"><span data-stu-id="d2e96-132">The ASP.NET MVC Web site</span></span>](https://asp.net/mvc/)
- [<span data-ttu-id="d2e96-133">ASP.NET MVC 论坛</span><span class="sxs-lookup"><span data-stu-id="d2e96-133">The ASP.NET MVC forums</span></span>](https://forums.asp.net/1146.aspx)

## <a id="_TOC2"></a><span data-ttu-id="d2e96-134">升级到 ASP.NET MVC 2 的 ASP.NET MVC 1.0 项目</span><span class="sxs-lookup"><span data-stu-id="d2e96-134">Upgrading an ASP.NET MVC 1.0 Project to ASP.NET MVC 2</span></span>

<span data-ttu-id="d2e96-135">ASP.NET MVC 2 可以在相同的服务器，从而使应用程序开发人员可以灵活地选择何时 ASP.NET MVC 1.0 应用程序升级到 ASP.NET MVC 2 上的与 ASP.NET MVC 1.0 并行安装。</span><span class="sxs-lookup"><span data-stu-id="d2e96-135">ASP.NET MVC 2 can be installed side by side with ASP.NET MVC 1.0 on the same server, which gives application developers flexibility in choosing when to upgrade an ASP.NET MVC 1.0 application to ASP.NET MVC 2.</span></span> <span data-ttu-id="d2e96-136">有关如何升级的信息，请参阅文档[升级 ASP.NET MVC 1.0 应用程序到 ASP.NET MVC 2](https://go.microsoft.com/fwlink/?LinkID=185459)。</span><span class="sxs-lookup"><span data-stu-id="d2e96-136">For information on how to upgrade, see the document [Upgrading an ASP.NET MVC 1.0 Application to ASP.NET MVC 2](https://go.microsoft.com/fwlink/?LinkID=185459).</span></span>

## <a id="_TOC3"></a><span data-ttu-id="d2e96-137">新功能</span><span class="sxs-lookup"><span data-stu-id="d2e96-137">New Features</span></span>

<span data-ttu-id="d2e96-138">本部分介绍已引入的功能在 MVC 2 版本中。</span><span class="sxs-lookup"><span data-stu-id="d2e96-138">This section describes features that have been introduced in the MVC 2 release.</span></span>

### <a id="_TOC3_1"></a><span data-ttu-id="d2e96-139">模板化帮助器</span><span class="sxs-lookup"><span data-stu-id="d2e96-139">Templated Helpers</span></span>

<span data-ttu-id="d2e96-140">模板化帮助器让你自动相关联的 HTML 元素，以进行编辑，并显示与数据类型。</span><span class="sxs-lookup"><span data-stu-id="d2e96-140">Templated helpers let you automatically associate HTML elements for edit and display with data types.</span></span> <span data-ttu-id="d2e96-141">例如，当在视图中显示 System.DateTime 类型的数据时，日期选取器 UI 元素可以自动呈现。</span><span class="sxs-lookup"><span data-stu-id="d2e96-141">For example, when data of type System.DateTime is displayed in a view, a date-picker UI element can be automatically rendered.</span></span> <span data-ttu-id="d2e96-142">这是类似于字段模板在 ASP.NET 动态数据中的工作方式。</span><span class="sxs-lookup"><span data-stu-id="d2e96-142">This is similar to how field templates work in ASP.NET Dynamic Data.</span></span> <span data-ttu-id="d2e96-143">有关详细信息，请参阅[使用模板化帮助器添加到显示数据](https://go.microsoft.com/fwlink/?LinkId=159062)MSDN 网站上。</span><span class="sxs-lookup"><span data-stu-id="d2e96-143">For more information, see [Using Templated Helpers to Display Data](https://go.microsoft.com/fwlink/?LinkId=159062) on the MSDN Web site.</span></span>

### <a id="_TOC3_2"></a><span data-ttu-id="d2e96-144">区域</span><span class="sxs-lookup"><span data-stu-id="d2e96-144">Areas</span></span>

<span data-ttu-id="d2e96-145">区域中，可以将大型项目组织到多个较小的部分，若要管理的大型 Web 应用程序的复杂性。</span><span class="sxs-lookup"><span data-stu-id="d2e96-145">Areas let you organize a large project into multiple smaller sections in order to manage the complexity of a large Web application.</span></span> <span data-ttu-id="d2e96-146">通常，每个部分 （"区域"） 表示大型网站的单独部分，并用于进行分组的控制器和视图的相关的集。</span><span class="sxs-lookup"><span data-stu-id="d2e96-146">Each section ("area") typically represents a separate section of a large Web site and is used to group related sets of controllers and views.</span></span> <span data-ttu-id="d2e96-147">有关详细信息，请参阅[演练： 将 ASP.NET MVC 应用程序按区域组织](https://go.microsoft.com/fwlink/?LinkId=158978)MSDN 网站上。</span><span class="sxs-lookup"><span data-stu-id="d2e96-147">For more information, see [Walkthrough: Organizing an ASP.NET MVC Application by Areas](https://go.microsoft.com/fwlink/?LinkId=158978) on the MSDN Web site.</span></span>

<span data-ttu-id="d2e96-148">若要创建新的区域中，在解决方案资源管理器中，右键单击项目，单击添加，然后单击区域。</span><span class="sxs-lookup"><span data-stu-id="d2e96-148">To create a new area, in Solution Explorer, right-click the project, click Add, and then click Area.</span></span> <span data-ttu-id="d2e96-149">此时将显示一个对话框，提示您输入区域名称。</span><span class="sxs-lookup"><span data-stu-id="d2e96-149">This displays a dialog box that prompts you for the area name.</span></span> <span data-ttu-id="d2e96-150">输入的区域名称后，Visual Studio 向项目中添加一个新的区域。</span><span class="sxs-lookup"><span data-stu-id="d2e96-150">After you enter the area name, Visual Studio adds a new area to the project.</span></span>

<span data-ttu-id="d2e96-151">下图显示具有两个区域，管理员和博客的项目的布局示例。</span><span class="sxs-lookup"><span data-stu-id="d2e96-151">The following figure shows an example layout for a project with two areas, Admin and Blogs.</span></span>

![](what-is-new-in-aspnet-mvc/_static/image1.png)

<span data-ttu-id="d2e96-152">当你创建一个区域后时，Visual Studio 将添加到每个区域从 AreaRegistration 派生的类。</span><span class="sxs-lookup"><span data-stu-id="d2e96-152">When you create an area, Visual Studio adds a class that derives from AreaRegistration to each area.</span></span> <span data-ttu-id="d2e96-153">此类则需要执行注册的区域和其路由中，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="d2e96-153">This class is required in order to register the area and its routes, as shown in the following example:</span></span>

[!code-csharp[Main](what-is-new-in-aspnet-mvc/samples/sample1.cs)]

<span data-ttu-id="d2e96-154">ASP.NET MVC 2 的默认项目模板包括对 RegisterAllAreas 方法的调用中的 Global.asax 文件的代码。</span><span class="sxs-lookup"><span data-stu-id="d2e96-154">The default project template for ASP.NET MVC 2 includes a call to the RegisterAllAreas method in the code for the Global.asax file.</span></span> <span data-ttu-id="d2e96-155">通过寻找从 AreaRegistration 类派生的所有类型、 实例化类型的实例，然后调用的实例上的 RegisterArea 方法还原时，此方法注册项目中的每个区域。</span><span class="sxs-lookup"><span data-stu-id="d2e96-155">This method registers each area in the project by looking for all types that derive from the AreaRegistration class, instantiating an instance of the type, and then calling the RegisterArea method on the instance.</span></span> <span data-ttu-id="d2e96-156">下面的示例演示如何做到这一点。</span><span class="sxs-lookup"><span data-stu-id="d2e96-156">The following example shows how this is done.</span></span>

[!code-csharp[Main](what-is-new-in-aspnet-mvc/samples/sample2.cs)]

<span data-ttu-id="d2e96-157">如果你不通过调用上下文 RegisterArea 方法中指定命名空间。默认情况下使用 Namespaces.Add 方法，注册类的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d2e96-157">If you do not specify the namespace in the RegisterArea method by calling the context.Namespaces.Add method, the namespace of the registration class is used by default.</span></span>

### <a id="_TOC3_3"></a><span data-ttu-id="d2e96-158">对异步控制器的支持</span><span class="sxs-lookup"><span data-stu-id="d2e96-158">Support for Asynchronous Controllers</span></span>

<span data-ttu-id="d2e96-159">ASP.NET MVC 2 现在允许控制器以进行异步处理请求。</span><span class="sxs-lookup"><span data-stu-id="d2e96-159">ASP.NET MVC 2 now allows controllers to process requests asynchronously.</span></span> <span data-ttu-id="d2e96-160">这可以允许频繁调用阻止操作 （例如网络请求） 以改为调用非阻塞对应的服务器，从而导致性能提升。</span><span class="sxs-lookup"><span data-stu-id="d2e96-160">This can lead to performance gains by allowing servers which frequently call blocking operations (like network requests) to call non-blocking counterparts instead.</span></span> <span data-ttu-id="d2e96-161">有关详细信息，请参阅[在 ASP.NET MVC 中使用异步控制器](https://msdn.microsoft.com/en-us/library/ee728598(v=VS.100).aspx)MSDN 上的主题。</span><span class="sxs-lookup"><span data-stu-id="d2e96-161">For more information, see the [Using an Asynchronous Controller in ASP.NET MVC](https://msdn.microsoft.com/en-us/library/ee728598(v=VS.100).aspx) topic on MSDN.</span></span>

### <a id="_TOC3_4"></a><span data-ttu-id="d2e96-162">DefaultValueAttribute 操作方法参数中的支持</span><span class="sxs-lookup"><span data-stu-id="d2e96-162">Support for DefaultValueAttribute in Action-Method Parameters</span></span>

<span data-ttu-id="d2e96-163">System.ComponentModel.DefaultValueAttribute 类允许为操作方法的自变量参数提供的默认值。</span><span class="sxs-lookup"><span data-stu-id="d2e96-163">The System.ComponentModel.DefaultValueAttribute class allows a default value to be supplied for the argument parameter to an action method.</span></span> <span data-ttu-id="d2e96-164">例如，假定定义以下默认路由：</span><span class="sxs-lookup"><span data-stu-id="d2e96-164">For example, assume that the following default route is defined:</span></span>

[!code-json[Main](what-is-new-in-aspnet-mvc/samples/sample3.json)]

<span data-ttu-id="d2e96-165">此外假定以下控制器和操作方法定义：</span><span class="sxs-lookup"><span data-stu-id="d2e96-165">Also assume that the following controller and action method is defined:</span></span>

[!code-csharp[Main](what-is-new-in-aspnet-mvc/samples/sample4.cs)]

<span data-ttu-id="d2e96-166">以下请求的任何 Url 将调用在前面的示例中定义的视图操作方法。</span><span class="sxs-lookup"><span data-stu-id="d2e96-166">Any of the following request URLs will invoke the View action method that is defined in the preceding example.</span></span>

- <span data-ttu-id="d2e96-167">/ 文章/视图/123</span><span class="sxs-lookup"><span data-stu-id="d2e96-167">/Article/View/123</span></span>
- <span data-ttu-id="d2e96-168">/ 文章/视图/123？ 页 = 1 （有效地与相同以前的请求）</span><span class="sxs-lookup"><span data-stu-id="d2e96-168">/Article/View/123?page=1 (Effectively the same as the previous request)</span></span>
- <span data-ttu-id="d2e96-169">/ 文章/视图/123？ 页 = 2</span><span class="sxs-lookup"><span data-stu-id="d2e96-169">/Article/View/123?page=2</span></span>

<span data-ttu-id="d2e96-170">DefaultValueAttribute 属性中，从前面的列表的第一个 URL 就将无法工作，因为页自变量是不可为 null 的值类型未提供其值。</span><span class="sxs-lookup"><span data-stu-id="d2e96-170">Without the DefaultValueAttribute attribute, the first URL from the preceding list would not work, because the page argument is a non-nullable value type whose value has not been provided.</span></span>

<span data-ttu-id="d2e96-171">如果在 Visual Basic 2010 或 Visual C# 2010年中编写代码，你可以而不是 DefaultValueAttribute 属性中，使用可选参数，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="d2e96-171">If your code is written in Visual Basic 2010 or Visual C# 2010, you can use optional parameters instead of the DefaultValueAttribute attribute, as shown in the following example:</span></span>

[!code-vb[Main](what-is-new-in-aspnet-mvc/samples/sample5.vb)]

### <a id="_TOC3_5"></a><span data-ttu-id="d2e96-172">对绑定的二进制数据，模型联编程序的支持</span><span class="sxs-lookup"><span data-stu-id="d2e96-172">Support for Binding Binary Data with Model Binders</span></span>

<span data-ttu-id="d2e96-173">有两个新重载 Html.Hidden 帮助程序进行编码以 base 64 编码字符串形式的二进制值：</span><span class="sxs-lookup"><span data-stu-id="d2e96-173">There are two new overloads of the Html.Hidden helper that encode binary values as base-64-encoded strings:</span></span>

[!code-csharp[Main](what-is-new-in-aspnet-mvc/samples/sample6.cs)]

<span data-ttu-id="d2e96-174">典型用途是要在视图中嵌入对象的时间戳。</span><span class="sxs-lookup"><span data-stu-id="d2e96-174">A typical use is to embed a timestamp for an object in the view.</span></span> <span data-ttu-id="d2e96-175">例如，你的应用程序可能包括以下产品对象：</span><span class="sxs-lookup"><span data-stu-id="d2e96-175">For example, your application might include the following Product object:</span></span>

[!code-csharp[Main](what-is-new-in-aspnet-mvc/samples/sample7.cs)]

<span data-ttu-id="d2e96-176">编辑窗体可以呈现的形式，如下面的示例中所示的时间戳属性：</span><span class="sxs-lookup"><span data-stu-id="d2e96-176">An edit form can render the TimeStamp property in the form as shown in the following example:</span></span>

[!code-aspx[Main](what-is-new-in-aspnet-mvc/samples/sample8.aspx)]

<span data-ttu-id="d2e96-177">此标记将时间戳值的隐藏输入的元素呈现为 base 64 编码字符串类似于下面的示例：</span><span class="sxs-lookup"><span data-stu-id="d2e96-177">This markup renders a hidden input element with the timestamp value as a base-64-encoded string that resembles the following example:</span></span>

[!code-html[Main](what-is-new-in-aspnet-mvc/samples/sample9.html)]

<span data-ttu-id="d2e96-178">此窗体可能会转入有一个参数类型产品，操作方法，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="d2e96-178">This form might be posted to an action method that has an argument of type Product, as shown in the following example:</span></span>

[!code-csharp[Main](what-is-new-in-aspnet-mvc/samples/sample10.cs)]

<span data-ttu-id="d2e96-179">在操作方法中，原因是已发布的 base 64 编码字符串转换为字节数组正确填充的时间戳属性。</span><span class="sxs-lookup"><span data-stu-id="d2e96-179">In the action method, the TimeStamp property is populated correctly because the posted base-64-encoded string is converted to a byte array.</span></span>

### <a id="_TOC3_6"></a><span data-ttu-id="d2e96-180">ModelMetadata 和 ModelMetadataProvider 类</span><span class="sxs-lookup"><span data-stu-id="d2e96-180">ModelMetadata and ModelMetadataProvider Classes</span></span>

<span data-ttu-id="d2e96-181">ModelMetadataProvider 类提供了获取的视图中的模型的元数据的抽象。</span><span class="sxs-lookup"><span data-stu-id="d2e96-181">The ModelMetadataProvider class provides an abstraction for obtaining metadata for the model within a view.</span></span> <span data-ttu-id="d2e96-182">MVC 2 包括默认提供程序，可以提供 System.ComponentModel.DataAnnotations 命名空间中的特性公开元数据。</span><span class="sxs-lookup"><span data-stu-id="d2e96-182">MVC 2 includes a default provider that makes available the metadata that is exposed by the attributes in the System.ComponentModel.DataAnnotations namespace.</span></span> <span data-ttu-id="d2e96-183">它是可以创建提供来自其他数据存储，例如数据库或 XML 文件的元数据的元数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="d2e96-183">It is possible to create metadata providers that provide metadata from other data stores, such as databases or XML files.</span></span>

<span data-ttu-id="d2e96-184">ViewDataDictionary 该类会公开一个包含由 ModelMetadataProvider 类从模型中提取的元数据的 ModelMetadata 对象。</span><span class="sxs-lookup"><span data-stu-id="d2e96-184">The ViewDataDictionary class exposes a ModelMetadata object that contains the metadata that is extracted from the model by the ModelMetadataProvider class.</span></span> <span data-ttu-id="d2e96-185">这样的模板化帮助器来使用此元数据和相应地调整其输出。</span><span class="sxs-lookup"><span data-stu-id="d2e96-185">This enables the templated helpers to consume this metadata and adjust their output accordingly.</span></span>

<span data-ttu-id="d2e96-186">有关详细信息，请参阅的文档[ModelMetadata](https://msdn.microsoft.com/en-us/library/system.web.mvc.modelmetadataprovider(VS.100).aspx)和[ModelMetadataProvider](https://msdn.microsoft.com/en-us/library/system.web.mvc.modelmetadataprovider(VS.100).aspx)类。</span><span class="sxs-lookup"><span data-stu-id="d2e96-186">For more information, see the documentation for the [ModelMetadata](https://msdn.microsoft.com/en-us/library/system.web.mvc.modelmetadataprovider(VS.100).aspx) and [ModelMetadataProvider](https://msdn.microsoft.com/en-us/library/system.web.mvc.modelmetadataprovider(VS.100).aspx) classes.</span></span>

### <a id="_TOC3_7"></a><span data-ttu-id="d2e96-187">对 DataAnnotations 特性的支持</span><span class="sxs-lookup"><span data-stu-id="d2e96-187">Support for DataAnnotations Attributes</span></span>

<span data-ttu-id="d2e96-188">ASP.NET MVC 2 支持使用 RangeAttribute、 RequiredAttribute、 StringLengthAttribute 和 RegexAttribute 验证属性 （在 System.ComponentModel.DataAnnotations 命名空间中定义） 时你将绑定到一个模型以便提供输入验证。</span><span class="sxs-lookup"><span data-stu-id="d2e96-188">ASP.NET MVC 2 supports using the RangeAttribute, RequiredAttribute, StringLengthAttribute, and RegexAttribute validation attributes (defined in the System.ComponentModel.DataAnnotations namespace) when you bind to a model in order to provide input validation.</span></span>

<span data-ttu-id="d2e96-189">有关详细信息，请参阅[如何： 验证模型数据使用 DataAnnotations 属性](https://go.microsoft.com/fwlink/?LinkId=159063)MSDN 网站上。</span><span class="sxs-lookup"><span data-stu-id="d2e96-189">For more information, see [How to: Validate Model Data Using DataAnnotations Attributes](https://go.microsoft.com/fwlink/?LinkId=159063) on the MSDN Web site.</span></span> <span data-ttu-id="d2e96-190">演示如何使用这些属性的示例项目是可在下载[https://go.microsoft.com/fwlink/?LinkId=157753](https://go.microsoft.com/fwlink/?LinkId=157753)。</span><span class="sxs-lookup"><span data-stu-id="d2e96-190">A sample project that illustrates the use of these attributes is available for download at [https://go.microsoft.com/fwlink/?LinkId=157753](https://go.microsoft.com/fwlink/?LinkId=157753).</span></span>

### <a id="_TOC3_8"></a><span data-ttu-id="d2e96-191">模型验证程序提供程序</span><span class="sxs-lookup"><span data-stu-id="d2e96-191">Model-Validator Providers</span></span>

<span data-ttu-id="d2e96-192">模型验证提供程序类表示模型中提供验证逻辑的抽象。</span><span class="sxs-lookup"><span data-stu-id="d2e96-192">The model-validation provider class represents an abstraction that provides validation logic for the model.</span></span> <span data-ttu-id="d2e96-193">ASP.NET MVC 包括默认提供程序基于 System.ComponentModel.DataAnnotations 命名空间中包含的验证属性。</span><span class="sxs-lookup"><span data-stu-id="d2e96-193">ASP.NET MVC includes a default provider based on validation attributes that are included in the System.ComponentModel.DataAnnotations namespace.</span></span> <span data-ttu-id="d2e96-194">你还可以创建自己的验证提供程序到模型中定义自定义验证规则和自定义映射的验证规则。</span><span class="sxs-lookup"><span data-stu-id="d2e96-194">You can also create your own validation providers that define custom validation rules and custom mappings of validation rules to the model.</span></span> <span data-ttu-id="d2e96-195">有关详细信息，请参阅的文档[ModelValidatorProvider](https://msdn.microsoft.com/en-us/library/system.web.mvc.ModelValidatorProvider(VS.100).aspx)类。</span><span class="sxs-lookup"><span data-stu-id="d2e96-195">For more information, see the documentation for the [ModelValidatorProvider](https://msdn.microsoft.com/en-us/library/system.web.mvc.ModelValidatorProvider(VS.100).aspx) class.</span></span>

### <a id="_TOC3_9"></a><span data-ttu-id="d2e96-196">客户端验证</span><span class="sxs-lookup"><span data-stu-id="d2e96-196">Client-Side Validation</span></span>

<span data-ttu-id="d2e96-197">模型验证程序提供程序类公开可以由客户端验证库使用的 JSON 序列化数据的窗体中的浏览器的验证元数据。</span><span class="sxs-lookup"><span data-stu-id="d2e96-197">The model-validator provider class exposes validation metadata to the browser in the form of JSON-serialized data that can be consumed by a client-side validation library.</span></span> <span data-ttu-id="d2e96-198">ASP.NET MVC 2 包括客户端验证库和支持前文所述 DataAnnotations 命名空间验证特性的适配器。</span><span class="sxs-lookup"><span data-stu-id="d2e96-198">ASP.NET MVC 2 includes a client validation library and adapter that supports the DataAnnotations namespace validation attributes noted earlier.</span></span> <span data-ttu-id="d2e96-199">提供程序类还使您能够通过编写处理 JSON 数据和到备用的库的调用的适配器使用其他客户端验证库。</span><span class="sxs-lookup"><span data-stu-id="d2e96-199">The provider class also enables you to use other client-validation libraries by writing an adapter that processes the JSON data and calls into the alternate library.</span></span>

### <a id="_TOC3_10"></a><span data-ttu-id="d2e96-200">Visual Studio 2010 的新代码段</span><span class="sxs-lookup"><span data-stu-id="d2e96-200">New Code Snippets for Visual Studio 2010</span></span>

<span data-ttu-id="d2e96-201">使用 Visual Studio 2010 安装 ASP.NET MVC 2 的 HTML 代码段的一组。</span><span class="sxs-lookup"><span data-stu-id="d2e96-201">A set of HTML code snippets for ASP.NET MVC 2 is installed with Visual Studio 2010.</span></span> <span data-ttu-id="d2e96-202">若要在工具菜单中查看这些代码段的列表，选择代码片段管理器。</span><span class="sxs-lookup"><span data-stu-id="d2e96-202">To view a list of these snippets, in the Tools menu, select Code Snippets Manager.</span></span> <span data-ttu-id="d2e96-203">代表所选语言中，选择 HTML，然后对于位置，选择 ASP.NET MVC 2。</span><span class="sxs-lookup"><span data-stu-id="d2e96-203">For the language, select HTML, and for location, select ASP.NET MVC 2.</span></span> <span data-ttu-id="d2e96-204">有关如何使用代码段的详细信息，请参阅 Visual Studio 文档。</span><span class="sxs-lookup"><span data-stu-id="d2e96-204">For more information about how to use code snippets, see the Visual Studio documentation.</span></span>

### <a id="_TOC3_11"></a><span data-ttu-id="d2e96-205">新 RequireHttpsAttribute 操作筛选器</span><span class="sxs-lookup"><span data-stu-id="d2e96-205">New RequireHttpsAttribute Action Filter</span></span>

<span data-ttu-id="d2e96-206">ASP.NET MVC 2 包括一个新的 RequireHttpsAttribute 类，可应用于操作方法和控制器。</span><span class="sxs-lookup"><span data-stu-id="d2e96-206">ASP.NET MVC 2 includes a new RequireHttpsAttribute class that can be applied to action methods and controllers.</span></span> <span data-ttu-id="d2e96-207">默认情况下，筛选器将非 SSL HTTP 请求重定向为启用 SSL (HTTPS) 等效项。</span><span class="sxs-lookup"><span data-stu-id="d2e96-207">By default, the filter redirects a non-SSL (HTTP) request to the SSL-enabled (HTTPS) equivalent.</span></span>

### <a id="_TOC3_12"></a><span data-ttu-id="d2e96-208">重写的 HTTP 方法谓词</span><span class="sxs-lookup"><span data-stu-id="d2e96-208">Overriding the HTTP Method Verb</span></span>

<span data-ttu-id="d2e96-209">使用 REST 体系结构样式生成网站时，HTTP 谓词用于确定要为资源执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d2e96-209">When you build a Web site by using the REST architectural style, HTTP verbs are used to determine which action to perform for a resource.</span></span> <span data-ttu-id="d2e96-210">REST 要求的完整范围的常见的 HTTP 谓词，包括 GET、 PUT、 POST 和删除该应用程序支持。</span><span class="sxs-lookup"><span data-stu-id="d2e96-210">REST requires that applications support the full range of common HTTP verbs, including GET, PUT, POST, and DELETE.</span></span>

<span data-ttu-id="d2e96-211">ASP.NET MVC 2 包括可以应用于操作方法和该功能简洁的语法的新属性。</span><span class="sxs-lookup"><span data-stu-id="d2e96-211">ASP.NET MVC 2 includes new attributes that you can apply to action methods and that feature compact syntax.</span></span> <span data-ttu-id="d2e96-212">这些属性使 ASP.NET MVC，若要选择基于 HTTP 谓词的操作方法。</span><span class="sxs-lookup"><span data-stu-id="d2e96-212">These attributes enable ASP.NET MVC to select an action method based on the HTTP verb.</span></span> <span data-ttu-id="d2e96-213">在下面的示例中，POST 请求将调用的第一个操作方法和 PUT 请求将调用第二个操作方法。</span><span class="sxs-lookup"><span data-stu-id="d2e96-213">In the following example, a POST request will call the first action method and a PUT request will call the second action method.</span></span>

[!code-csharp[Main](what-is-new-in-aspnet-mvc/samples/sample11.cs)]

<span data-ttu-id="d2e96-214">在早期版本的 ASP.NET MVC，这些操作所需方法更详细的语法，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="d2e96-214">In earlier versions of ASP.NET MVC, these action methods required more verbose syntax, as shown in the following example:</span></span>

[!code-csharp[Main](what-is-new-in-aspnet-mvc/samples/sample12.cs)]

<span data-ttu-id="d2e96-215">由于浏览器支持仅的 GET 和 POST HTTP 谓词，则不可以发布到需要不同的谓词的操作。</span><span class="sxs-lookup"><span data-stu-id="d2e96-215">Because browsers support only the GET and POST HTTP verbs, it is not possible to post to an action that requires a different verb.</span></span> <span data-ttu-id="d2e96-216">因此不可能以本机方式支持 rest 样式的所有请求。</span><span class="sxs-lookup"><span data-stu-id="d2e96-216">Thus it is not possible to natively support all RESTful requests.</span></span>

<span data-ttu-id="d2e96-217">但是，以支持基于 Rest 请求在 POST 期间，ASP.NET MVC 2 引入一个新的 HttpMethodOverride HTML 帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="d2e96-217">However, to support RESTful requests during POST operations, ASP.NET MVC 2 introduces a new HttpMethodOverride HTML helper method.</span></span> <span data-ttu-id="d2e96-218">此方法呈现一个隐藏的输入的元素，使窗体来有效地模拟任何 HTTP 方法。</span><span class="sxs-lookup"><span data-stu-id="d2e96-218">This method renders a hidden input element that causes the form to effectively emulate any HTTP method.</span></span> <span data-ttu-id="d2e96-219">例如，通过使用 HttpMethodOverride HTML 帮助器方法，你可以显示的提交窗体是 PUT 或 DELETE 请求。</span><span class="sxs-lookup"><span data-stu-id="d2e96-219">For example, by using the HttpMethodOverride HTML helper method, you can have a form submission appear be a PUT or DELETE request.</span></span> <span data-ttu-id="d2e96-220">HttpMethodOverride 的行为会影响以下属性：</span><span class="sxs-lookup"><span data-stu-id="d2e96-220">The behavior of HttpMethodOverride affects the following attributes:</span></span>

- <span data-ttu-id="d2e96-221">HttpPostAttribute</span><span class="sxs-lookup"><span data-stu-id="d2e96-221">HttpPostAttribute</span></span>
- <span data-ttu-id="d2e96-222">HttpPutAttribute</span><span class="sxs-lookup"><span data-stu-id="d2e96-222">HttpPutAttribute</span></span>
- <span data-ttu-id="d2e96-223">HttpGetAttribute</span><span class="sxs-lookup"><span data-stu-id="d2e96-223">HttpGetAttribute</span></span>
- <span data-ttu-id="d2e96-224">HttpDeleteAttribute</span><span class="sxs-lookup"><span data-stu-id="d2e96-224">HttpDeleteAttribute</span></span>
- <span data-ttu-id="d2e96-225">AcceptVerbsAttribute</span><span class="sxs-lookup"><span data-stu-id="d2e96-225">AcceptVerbsAttribute</span></span>

<span data-ttu-id="d2e96-226">隐藏的输入的元素，并且在其名称 X HTTP 的方法重写其值设置为 HTTP 谓词来模拟。</span><span class="sxs-lookup"><span data-stu-id="d2e96-226">The hidden input element has its name X-HTTP-Method-Override and its value set to the HTTP verb to emulate.</span></span> <span data-ttu-id="d2e96-227">替代值可以还在 HTTP 标头或指定查询字符串值作为名称/值对。</span><span class="sxs-lookup"><span data-stu-id="d2e96-227">The override value can also be specified in an HTTP header or in a query string value as a name/value pair.</span></span>

<span data-ttu-id="d2e96-228">实际请求时 POST 请求，则仅可以使用替代。</span><span class="sxs-lookup"><span data-stu-id="d2e96-228">The override can only be used when the real request is a POST request.</span></span> <span data-ttu-id="d2e96-229">使用任何其他 HTTP 谓词的请求将被忽略的替代值。</span><span class="sxs-lookup"><span data-stu-id="d2e96-229">The override value will be ignored for requests that use any other HTTP verb.</span></span>

### <a id="_TOC3_13"></a><span data-ttu-id="d2e96-230">模板化帮助器的新 HiddenInputAttribute 类</span><span class="sxs-lookup"><span data-stu-id="d2e96-230">New HiddenInputAttribute Class for Templated Helpers</span></span>

<span data-ttu-id="d2e96-231">你可以将新的 HiddenInputAttribute 特性应用于模型属性，以指示编辑器模板中显示该模型时是否应呈现隐藏的输入的元素。</span><span class="sxs-lookup"><span data-stu-id="d2e96-231">You can apply the new HiddenInputAttribute attribute to a model property to indicate whether a hidden input element should be rendered when displaying the model in an editor template.</span></span> <span data-ttu-id="d2e96-232">（该属性设置 HiddenInput 隐式 UIHint 值）。</span><span class="sxs-lookup"><span data-stu-id="d2e96-232">(The attribute sets an implicit UIHint value of HiddenInput).</span></span> <span data-ttu-id="d2e96-233">该特性的 DisplayValue 属性，可以指定是否在编辑器中显示值和显示模式。</span><span class="sxs-lookup"><span data-stu-id="d2e96-233">The attribute's DisplayValue property lets you specify whether the value is displayed in editor and display modes.</span></span> <span data-ttu-id="d2e96-234">当 DisplayValue 设置为 false 时，将不会显示，甚至不通常环绕字段的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="d2e96-234">When DisplayValue is set to false, nothing is displayed, not even the HTML markup that normally surrounds a field.</span></span> <span data-ttu-id="d2e96-235">DisplayValue 的默认值为 true。</span><span class="sxs-lookup"><span data-stu-id="d2e96-235">The default value for DisplayValue is true.</span></span>

<span data-ttu-id="d2e96-236">在以下情况下，可以使用 HiddenInputAttribute 属性：</span><span class="sxs-lookup"><span data-stu-id="d2e96-236">You might use HiddenInputAttribute attribute in the following scenarios:</span></span>

- <span data-ttu-id="d2e96-237">当视图可让用户编辑的对象 ID，并且有必要的值以及显示并提供一个隐藏的输入的元素，以便它可以传递到控制器包含旧的 ID。</span><span class="sxs-lookup"><span data-stu-id="d2e96-237">When a view lets users edit the ID of an object and it is necessary to display the value as well as to provide a hidden input element that contains the old ID so that it can be passed back to the controller.</span></span>
- <span data-ttu-id="d2e96-238">当视图允许用户编辑应永远不会显示，例如时间戳属性的二进制属性。</span><span class="sxs-lookup"><span data-stu-id="d2e96-238">When a view lets users edit a binary property that should never be displayed, such as a timestamp property.</span></span> <span data-ttu-id="d2e96-239">在这种情况下，不显示的值和 （如 label 和值） 的周围 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="d2e96-239">In that case, the value and surrounding HTML markup (such as the label and value) are not displayed.</span></span>

<span data-ttu-id="d2e96-240">下面的示例演示如何使用 HiddenInputAttribute 类。</span><span class="sxs-lookup"><span data-stu-id="d2e96-240">The following example shows how to use the HiddenInputAttribute class.</span></span>

[!code-csharp[Main](what-is-new-in-aspnet-mvc/samples/sample13.cs)]

<span data-ttu-id="d2e96-241">如果将属性设置为 true （或未指定任何参数），将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="d2e96-241">When the attribute is set to true (or no parameter is specified), the following occurs:</span></span>

- <span data-ttu-id="d2e96-242">在显示模板中，标签将呈现在和的值显示给用户。</span><span class="sxs-lookup"><span data-stu-id="d2e96-242">In display templates, a label is rendered and the value is displayed to the user.</span></span>
- <span data-ttu-id="d2e96-243">编辑器模板中呈现标签和值呈现中隐藏的输入元素。</span><span class="sxs-lookup"><span data-stu-id="d2e96-243">In editor templates, a label is rendered and the value is rendered in a hidden input element.</span></span>

<span data-ttu-id="d2e96-244">当该属性设置为 false 时，发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="d2e96-244">When the attribute is set to false, the following occurs:</span></span>

- <span data-ttu-id="d2e96-245">显示模板中执行任何操作被呈现为该字段。</span><span class="sxs-lookup"><span data-stu-id="d2e96-245">In display templates, nothing is rendered for that field.</span></span>
- <span data-ttu-id="d2e96-246">编辑器模板中没有标签将呈现在和中隐藏的输入元素呈现值。</span><span class="sxs-lookup"><span data-stu-id="d2e96-246">In editor templates, no label is rendered and the value is rendered in a hidden input element.</span></span>

### <a id="_TOC3_14"></a><span data-ttu-id="d2e96-247">Html.ValidationSummary 帮助器方法可以显示模型级别错误</span><span class="sxs-lookup"><span data-stu-id="d2e96-247">Html.ValidationSummary Helper Method Can Display Model-Level Errors</span></span>

<span data-ttu-id="d2e96-248">而不是始终显示所有验证错误，Html.ValidationSummary 帮助器方法具有显示仅模型级别错误的新选项。</span><span class="sxs-lookup"><span data-stu-id="d2e96-248">Instead of always displaying all validation errors, the Html.ValidationSummary helper method has a new option to display only model-level errors.</span></span> <span data-ttu-id="d2e96-249">这使模型级别错误，以验证摘要中显示和特定于字段的错误，以显示每个字段旁边。</span><span class="sxs-lookup"><span data-stu-id="d2e96-249">This enables model-level errors to be displayed in the validation summary and field-specific errors to be displayed next to each field.</span></span>

### <a id="_TOC3_15"></a><span data-ttu-id="d2e96-250">在 Visual Studio 生成的代码是特定的 T4 模板到.NET framework 目标版本</span><span class="sxs-lookup"><span data-stu-id="d2e96-250">T4 Templates in Visual Studio Generate Code that is Specific to the Target Version of the .NET Framework</span></span>

<span data-ttu-id="d2e96-251">一个新属性是可用的 T4 文件从指向指定应用程序使用的.NET framework 版本的 ASP.NET MVC T4 主机。</span><span class="sxs-lookup"><span data-stu-id="d2e96-251">A new property is available to T4 files from the ASP.NET MVC T4 host that specifies the version of the .NET Framework that is used by the application.</span></span> <span data-ttu-id="d2e96-252">这使 T4 模板生成代码和特定于.NET Framework 的版本的标记。</span><span class="sxs-lookup"><span data-stu-id="d2e96-252">This enables T4 templates to generate code and markup that is specific to a version of the .NET Framework.</span></span> <span data-ttu-id="d2e96-253">在 Visual Studio 2008 中，此值始终是.NET 3.5。</span><span class="sxs-lookup"><span data-stu-id="d2e96-253">In Visual Studio 2008, the value is always .NET 3.5.</span></span> <span data-ttu-id="d2e96-254">在 Visual Studio 2010 中，值为.NET 3.5 或.NET 4。</span><span class="sxs-lookup"><span data-stu-id="d2e96-254">In Visual Studio 2010, the value is either .NET 3.5 or .NET 4.</span></span>

## <a id="_TOC4"></a><span data-ttu-id="d2e96-255">API 改进</span><span class="sxs-lookup"><span data-stu-id="d2e96-255">API Improvements</span></span>

<span data-ttu-id="d2e96-256">本部分介绍对现有的 ASP.NET MVC 类型和成员的更改。</span><span class="sxs-lookup"><span data-stu-id="d2e96-256">This section describes changes to existing ASP.NET MVC types and members.</span></span>

- <span data-ttu-id="d2e96-257">在控制器类中添加受保护的虚拟 CreateActionInvoker 方法。</span><span class="sxs-lookup"><span data-stu-id="d2e96-257">Added a protected virtual CreateActionInvoker method in the Controller class.</span></span> <span data-ttu-id="d2e96-258">此方法调用由控制器的 ActionInvoker 属性，如果已设置没有调用程序，则允许调用方的延迟实例化。</span><span class="sxs-lookup"><span data-stu-id="d2e96-258">This method is invoked by the ActionInvoker property of Controller and allows for lazy instantiation of the invoker if no invoker is already set.</span></span>
- <span data-ttu-id="d2e96-259">AuthorizeAttribute 类中添加受保护的虚拟 HandleUnauthorizedRequest 方法。</span><span class="sxs-lookup"><span data-stu-id="d2e96-259">Added a protected virtual HandleUnauthorizedRequest method in the AuthorizeAttribute class.</span></span> <span data-ttu-id="d2e96-260">这使派生 AuthorizeAttribute 来控制授权失败时的行为的筛选器。</span><span class="sxs-lookup"><span data-stu-id="d2e96-260">This enables filters that derive from AuthorizeAttribute to control the behavior when authorization fails.</span></span>
- <span data-ttu-id="d2e96-261">ValueProviderDictionary 类中添加一个 Add （字符串，对象键值） 方法。</span><span class="sxs-lookup"><span data-stu-id="d2e96-261">Added an Add(string key, object value) method in the ValueProviderDictionary class.</span></span> <span data-ttu-id="d2e96-262">这使您能够为 ValueProviderDictionary，使用字典初始值设定项语法，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="d2e96-262">This enables you to use the dictionary initializer syntax for ValueProviderDictionary, as in the following example:</span></span>

[!code-csharp[Main](what-is-new-in-aspnet-mvc/samples/sample14.cs)]

- <span data-ttu-id="d2e96-263">添加 get\_对象 Sys.Mvc.AjaxContext 类中的方法。</span><span class="sxs-lookup"><span data-stu-id="d2e96-263">Added a get\_object method in the Sys.Mvc.AjaxContext class.</span></span> <span data-ttu-id="d2e96-264">这是类似于 get JavaScript 方法\_数据方法，但如果响应的内容类型为 application/json，获取\_对象返回的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="d2e96-264">This is a JavaScript method that is similar to the get\_data method, but if the content type of the response is application/json, get\_object returns the JSON object.</span></span>
- <span data-ttu-id="d2e96-265">AuthorizationContext 类中添加 ActionDescriptor 属性。</span><span class="sxs-lookup"><span data-stu-id="d2e96-265">Added an ActionDescriptor property in the AuthorizationContext class.</span></span>
- <span data-ttu-id="d2e96-266">添加可以用于绑定到包含任何 ID 属性，该属性不存在时的模型时要解决问题的 UrlParameter.Optional 令牌在窗体发布请求。</span><span class="sxs-lookup"><span data-stu-id="d2e96-266">Added a UrlParameter.Optional token that can be used to work around problems when binding to a model that contains an ID property when the property is absent in a form post.</span></span> <span data-ttu-id="d2e96-267">有关详细信息，请参阅输入[ASP.NET MVC 2 可选 URL 参数](http://haacked.com/archive/2010/02/12/asp-net-mvc-2-optional-url-parameters.aspx)Phil Haack 博客上。</span><span class="sxs-lookup"><span data-stu-id="d2e96-267">For more detail, see the entry [ASP.NET MVC 2 Optional URL Parameters](http://haacked.com/archive/2010/02/12/asp-net-mvc-2-optional-url-parameters.aspx) on Phil Haack's blog.</span></span>

## <a id="_TOC5"></a><span data-ttu-id="d2e96-268">重大更改</span><span class="sxs-lookup"><span data-stu-id="d2e96-268">Breaking Changes</span></span>

<span data-ttu-id="d2e96-269">以下的更改可能导致现有的 ASP.NET MVC 1.0 应用程序中出现错误。</span><span class="sxs-lookup"><span data-stu-id="d2e96-269">The following changes might cause errors in existing ASP.NET MVC 1.0 applications.</span></span>

#### <a name="change-in-property-validation-behavior-for-classes-that-implement-idataerrorinfo"></a><span data-ttu-id="d2e96-270">在实现 IDataErrorInfo 的类的属性验证行为更改</span><span class="sxs-lookup"><span data-stu-id="d2e96-270">Change in property validation behavior for classes that implement IDataErrorInfo</span></span>

<span data-ttu-id="d2e96-271">对于使用 IDataErrorInfo 来执行验证的模型对象，是来验证每个属性，无论是否已设置新值。</span><span class="sxs-lookup"><span data-stu-id="d2e96-271">For model objects that use IDataErrorInfo to perform validation, every property is validated, regardless of whether a new value was set.</span></span> <span data-ttu-id="d2e96-272">在 ASP.NET MVC 1.0 中，已验证设置的新值的属性。</span><span class="sxs-lookup"><span data-stu-id="d2e96-272">In ASP.NET MVC 1.0, only properties that had new values set were validated.</span></span> <span data-ttu-id="d2e96-273">在 ASP.NET MVC 2 中，仅当所有属性验证程序都已成功调用 IDataErrorInfo 错误属性。</span><span class="sxs-lookup"><span data-stu-id="d2e96-273">In ASP.NET MVC 2, the Error property of IDataErrorInfo is called only if all the property validators were successful.</span></span>

#### <a name="iis-script-mapping-script-is-no-longer-available-in-the-installer"></a><span data-ttu-id="d2e96-274">IIS 脚本映射脚本不再可用在安装程序</span><span class="sxs-lookup"><span data-stu-id="d2e96-274">IIS script mapping script is no longer available in the installer</span></span>

<span data-ttu-id="d2e96-275">IIS 的脚本映射脚本是用于配置为 IIS 6 和 IIS 7 在经典模式下的脚本映射的命令行脚本。</span><span class="sxs-lookup"><span data-stu-id="d2e96-275">The IIS script-mapping script is a command-line script that is used to configure script maps for IIS 6 and for IIS 7 in Classic mode.</span></span> <span data-ttu-id="d2e96-276">如果你使用 Visual Studio 开发服务器，或在集成模式下使用 IIS 7，则不需要的脚本映射脚本。</span><span class="sxs-lookup"><span data-stu-id="d2e96-276">The script-mapping script is not needed if you use the Visual Studio Development Server or if you use IIS 7 in Integrated mode.</span></span> <span data-ttu-id="d2e96-277">脚本都是作为单独的不受支持下载上可用[ASP.NET WebStack](https://github.com/aspnet/AspNetWebStack)。</span><span class="sxs-lookup"><span data-stu-id="d2e96-277">The scripts are available as a separate unsupported download on the [ASP.NET WebStack](https://github.com/aspnet/AspNetWebStack).</span></span>

#### <a name="the-htmlsubstitute-helper-method-in-mvc-futures-is-no-longer-available"></a><span data-ttu-id="d2e96-278">在 MVC Future 的 Html.Substitute 帮助器方法不再可用</span><span class="sxs-lookup"><span data-stu-id="d2e96-278">The Html.Substitute helper method in MVC Futures is no longer available</span></span>

<span data-ttu-id="d2e96-279">MVC 视图引擎的呈现行为发生变化，由于 Html.Substitute 帮助器方法不起作用，并已删除。</span><span class="sxs-lookup"><span data-stu-id="d2e96-279">Due to changes in the rendering behavior of MVC view engines, the Html.Substitute helper method does not work and has been removed.</span></span>

#### <a name="the-ivalueprovider-interface-replaces-all-uses-of-idictionary"></a><span data-ttu-id="d2e96-280">IValueProvider 接口替换所有使用 IDictionary</span><span class="sxs-lookup"><span data-stu-id="d2e96-280">The IValueProvider interface replaces all uses of IDictionary</span></span>

<span data-ttu-id="d2e96-281">现在接受 IDictionary 在 MVC 1.0 中的每个属性或方法参数接受 IValueProvider。</span><span class="sxs-lookup"><span data-stu-id="d2e96-281">Every property or method argument that accepted IDictionary in MVC 1.0 now accepts IValueProvider.</span></span> <span data-ttu-id="d2e96-282">此更改影响仅包括自定义值在提供程序或自定义模型联编程序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d2e96-282">This change affects only applications that include custom value providers or custom model binders.</span></span> <span data-ttu-id="d2e96-283">属性和受此更改的方法的示例包括：</span><span class="sxs-lookup"><span data-stu-id="d2e96-283">Examples of properties and methods that are affected by this change include the following:</span></span>

- <span data-ttu-id="d2e96-284">ControllerBase 和 ModelBindingContext 类 ValueProvider 属性。</span><span class="sxs-lookup"><span data-stu-id="d2e96-284">The ValueProvider property of the ControllerBase and ModelBindingContext classes.</span></span>
- <span data-ttu-id="d2e96-285">控制器类 TryUpdateModel 方法。</span><span class="sxs-lookup"><span data-stu-id="d2e96-285">The TryUpdateModel methods of the Controller class.</span></span>

#### <a name="new-css-classes-were-added-in-the-sitecss-file"></a><span data-ttu-id="d2e96-286">Site.css 文件中添加新的 CSS 类</span><span class="sxs-lookup"><span data-stu-id="d2e96-286">New CSS classes were added in the Site.css file</span></span>

<span data-ttu-id="d2e96-287">中的 ASP.NET MVC 项目模板的 Site.css 文件已更新以包括验证功能以及的模板化帮助器使用的新样式。</span><span class="sxs-lookup"><span data-stu-id="d2e96-287">The Site.css file in the ASP.NET MVC project templates has been updated to include new styles used by the validation functionality and by the templated helpers.</span></span>

#### <a name="helpers-now-return-an-mvchtmlstring-object"></a><span data-ttu-id="d2e96-288">帮助器现在返回 MvcHtmlString 对象</span><span class="sxs-lookup"><span data-stu-id="d2e96-288">Helpers now return an MvcHtmlString object</span></span>

<span data-ttu-id="d2e96-289">为了利用新的 HTML 编码表达式语法的 ASP.NET 4 中，HTML 帮助器的返回类型现 MvcHtmlString 而不是字符串。</span><span class="sxs-lookup"><span data-stu-id="d2e96-289">In order to take advantage of the new HTML-encoding expression syntax in ASP.NET 4, the return type for HTML helpers is now MvcHtmlString instead of a string.</span></span> <span data-ttu-id="d2e96-290">如果在 ASP.NET 3.5 上使用 ASP.NET MVC 2 和新的帮助器，你将不能充分利用的 HTML 编码的语法;仅当你在 ASP.NET 4 上运行 ASP.NET MVC 2 时，新的语法是可用。</span><span class="sxs-lookup"><span data-stu-id="d2e96-290">If you use ASP.NET MVC 2 and the new helpers on ASP.NET 3.5, you will not be able to take advantage of the HTML-encoding syntax; the new syntax is available only when you run ASP.NET MVC 2 on ASP.NET 4.</span></span>

#### <a name="jsonresult-now-responds-only-to-http-post-requests"></a><span data-ttu-id="d2e96-291">JsonResult 现在仅响应 HTTP POST 请求</span><span class="sxs-lookup"><span data-stu-id="d2e96-291">JsonResult now responds only to HTTP POST requests</span></span>

<span data-ttu-id="d2e96-292">以便降低劫持默认情况下，具有信息泄露的可能性攻击的 JSON JsonResult 类现在仅响应 HTTP POST 请求。</span><span class="sxs-lookup"><span data-stu-id="d2e96-292">In order to mitigate JSON hijacking attacks that have the potential for information disclosure, by default, the JsonResult class now responds only to HTTP POST requests.</span></span> <span data-ttu-id="d2e96-293">应更改 Ajax 获取对操作方法的调用返回 JsonResult 对象，以改为使用 POST。</span><span class="sxs-lookup"><span data-stu-id="d2e96-293">Ajax GET calls to action methods that return a JsonResult object should be changed to use POST instead.</span></span> <span data-ttu-id="d2e96-294">如有必要，你可以通过设置 JsonResult 的新 JsonRequestBehavior 属性重写此行为。</span><span class="sxs-lookup"><span data-stu-id="d2e96-294">If necessary, you can override this behavior by setting the new JsonRequestBehavior property of JsonResult.</span></span> <span data-ttu-id="d2e96-295">有关潜在漏洞的威胁的详细信息，请参阅博客文章[JSON 劫持](http://haacked.com/archive/2009/06/25/json-hijacking.aspx)Phil Haack 博客上。</span><span class="sxs-lookup"><span data-stu-id="d2e96-295">For more information about the potential exploit, see the blog post [JSON Hijacking](http://haacked.com/archive/2009/06/25/json-hijacking.aspx) on Phil Haack's blog.</span></span>

#### <a name="model-and-modeltype-property-setters-on-modelbindingcontext-are-obsolete"></a><span data-ttu-id="d2e96-296">模型和上 ModelBindingContext ModelType 属性 setter 中已过时</span><span class="sxs-lookup"><span data-stu-id="d2e96-296">Model and ModelType property setters on ModelBindingContext are obsolete</span></span>

<span data-ttu-id="d2e96-297">新的可设置 ModelMetadata 属性已添加到 ModelBindingContext 类。</span><span class="sxs-lookup"><span data-stu-id="d2e96-297">A new settable ModelMetadata property has been added to the ModelBindingContext class.</span></span> <span data-ttu-id="d2e96-298">新的属性封装模型和 ModelType 属性。</span><span class="sxs-lookup"><span data-stu-id="d2e96-298">The new property encapsulates both the Model and the ModelType properties.</span></span> <span data-ttu-id="d2e96-299">尽管的模型和 ModelType 属性已过时，但对于向后兼容性属性 getter 仍然可用;它们将委派给 ModelMetadata 属性来检索的值。</span><span class="sxs-lookup"><span data-stu-id="d2e96-299">Although the Model and ModelType properties are obsolete, for backward compatibility the property getters still work; they delegate to the ModelMetadata property to retrieve the value.</span></span>

#### <a name="changes-to-the-defaultcontrollerfactory-class-break-custom-controller-factories-that-derive-from-it"></a><span data-ttu-id="d2e96-300">对 DefaultControllerFactory 类更改中断从它派生的自定义控制器工厂</span><span class="sxs-lookup"><span data-stu-id="d2e96-300">Changes to the DefaultControllerFactory class break custom controller factories that derive from it</span></span>

<span data-ttu-id="d2e96-301">通过删除 requestcontext 已属性进行了修复 DefaultControllerFactory 类。</span><span class="sxs-lookup"><span data-stu-id="d2e96-301">The DefaultControllerFactory class was fixed by removing the RequestContext property.</span></span> <span data-ttu-id="d2e96-302">替代此属性，请求上下文实例传递给受保护的虚拟 GetControllerInstance 和 GetControllerType 方法。</span><span class="sxs-lookup"><span data-stu-id="d2e96-302">In place of this property, the request context instance is passed to the protected virtual GetControllerInstance and GetControllerType methods.</span></span> <span data-ttu-id="d2e96-303">此更改会影响从 DefaultControllerFactory 派生的自定义控制器工厂。</span><span class="sxs-lookup"><span data-stu-id="d2e96-303">This change affects custom controller factories that derive from DefaultControllerFactory.</span></span>

<span data-ttu-id="d2e96-304">自定义控制器工厂通常用于提供应用程序的 ASP.NET MVC 的依赖关系注入。</span><span class="sxs-lookup"><span data-stu-id="d2e96-304">Custom controller factories are often used to provide dependency injection for ASP.NET MVC applications.</span></span> <span data-ttu-id="d2e96-305">若要更新的自定义控制器工厂，以支持 ASP.NET MVC 2，更改方法签名或签名，以匹配新的签名和请求上下文参数使用而不是属性。</span><span class="sxs-lookup"><span data-stu-id="d2e96-305">To update the custom controller factories to support ASP.NET MVC 2, change the method signature or signatures to match the new signatures, and use the request context parameter instead of the property.</span></span>

#### <a name="area-is-a-now-a-reserved-route-value-key"></a><span data-ttu-id="d2e96-306">"区域"是保留的路由值密钥的现在</span><span class="sxs-lookup"><span data-stu-id="d2e96-306">"Area" is a now a reserved route-value key</span></span>

<span data-ttu-id="d2e96-307">路由值中的字符串"区域"现在在 ASP.NET MVC 中具有特殊含义，"控制器"和"操作"执行的相同方式。</span><span class="sxs-lookup"><span data-stu-id="d2e96-307">The string "area" in Route values now has special meaning in ASP.NET MVC, in the same way that "controller" and "action" do.</span></span> <span data-ttu-id="d2e96-308">一个含意为，如果 HTML 帮助器随附了一个包含"区域"的路由值字典，帮助程序将不再追加"区域"查询字符串中。</span><span class="sxs-lookup"><span data-stu-id="d2e96-308">One implication is that if HTML helpers are supplied with a route-value dictionary containing "area", the helpers will no longer append "area" in the query string.</span></span>

<span data-ttu-id="d2e96-309">如果你使用的区域功能，请确保不使用 {区} 作为路由 URL 的一部分。</span><span class="sxs-lookup"><span data-stu-id="d2e96-309">If you are using the Areas feature, make sure to not use {area} as part of your route URL.</span></span>


## <a id="_TOC6"></a><span data-ttu-id="d2e96-310">免责声明</span><span class="sxs-lookup"><span data-stu-id="d2e96-310">Disclaimer</span></span>

<span data-ttu-id="d2e96-311">这是一份初稿，并可能在本文所述软件最终商业发布之前进行大幅更改。</span><span class="sxs-lookup"><span data-stu-id="d2e96-311">This is a preliminary document and may be changed substantially prior to final commercial release of the software described herein.</span></span>

<span data-ttu-id="d2e96-312">本文所含信息代表 Microsoft Corporation 对截至发布之日所讨论问题持有的当前观点。</span><span class="sxs-lookup"><span data-stu-id="d2e96-312">The information contained in this document represents the current view of Microsoft Corporation on the issues discussed as of the date of publication.</span></span> <span data-ttu-id="d2e96-313">由于 Microsoft 必须对不断变化的市场情况作出响应，所以不应将本文解释为是 Microsoft 做出的承诺，Microsoft 并不保证所提供的任何信息在公布之日后的准确性。</span><span class="sxs-lookup"><span data-stu-id="d2e96-313">Because Microsoft must respond to changing market conditions, it should not be interpreted to be a commitment on the part of Microsoft, and Microsoft cannot guarantee the accuracy of any information presented after the date of publication.</span></span>

<span data-ttu-id="d2e96-314">本白皮书仅用于提供信息。</span><span class="sxs-lookup"><span data-stu-id="d2e96-314">This White Paper is for informational purposes only.</span></span> <span data-ttu-id="d2e96-315">MICROSOFT 对本文档中的信息不做任何明示、暗示或法定的担保。</span><span class="sxs-lookup"><span data-stu-id="d2e96-315">MICROSOFT MAKES NO WARRANTIES, EXPRESS, IMPLIED OR STATUTORY, AS TO THE INFORMATION IN THIS DOCUMENT.</span></span>

<span data-ttu-id="d2e96-316">遵守所有适用的著作权法是用户的责任。</span><span class="sxs-lookup"><span data-stu-id="d2e96-316">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="d2e96-317">未经 Microsoft Corporation 明确的书面许可，不得出于任何目的或以任何形式或任何手段（电子、机械、影印、记录或其他方法）复制本文档的任何部分，或者将其存储或引入检索系统，或者将其进行传播。受版权法保护的权利不受此限制。</span><span class="sxs-lookup"><span data-stu-id="d2e96-317">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="d2e96-318">对于本文档中的主题，Microsoft 可能具有专利、专利申请、商标、版权或其他知识产权。</span><span class="sxs-lookup"><span data-stu-id="d2e96-318">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="d2e96-319">除非 Microsoft 的任何书面许可协议明确提出，否则，本文档的提供并不表示 Microsoft 已将这些专利、商标、版权或其他知识产权的任何许可权限授予您。</span><span class="sxs-lookup"><span data-stu-id="d2e96-319">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="d2e96-320">除非另有声明，否则此处描述的示例公司、组织、产品、域名、电子邮件地址、徽标、人物、地点和事件都是虚构的，无意与任何真实的公司、组织、产品、域名、电子邮件地址、徽标、人物、地点或事件相关联，也不应进行这方面的推断。</span><span class="sxs-lookup"><span data-stu-id="d2e96-320">Unless otherwise noted, the example companies, organizations, products, domain names, e-mail addresses, logos, people, places and events depicted herein are fictitious, and no association with any real company, organization, product, domain name, email address, logo, person, place or event is intended or should be inferred.</span></span>

<span data-ttu-id="d2e96-321">© 2010 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="d2e96-321">© 2010 Microsoft Corporation.</span></span> <span data-ttu-id="d2e96-322">保留所有权利。</span><span class="sxs-lookup"><span data-stu-id="d2e96-322">All rights reserved.</span></span>

<span data-ttu-id="d2e96-323">Microsoft 和 Windows 是 Microsoft Corporation 在美国和/或其他国家/地区的注册商标或商标。</span><span class="sxs-lookup"><span data-stu-id="d2e96-323">Microsoft and Windows are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries.</span></span>

<span data-ttu-id="d2e96-324">此处提到的真实公司和产品的名称可能是其各自所有者的商标。</span><span class="sxs-lookup"><span data-stu-id="d2e96-324">The names of actual companies and products mentioned herein may be the trademarks of their respective owners.</span></span>