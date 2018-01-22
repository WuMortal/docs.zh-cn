---
title: "在 ASP.NET 核心中的应用程序部分"
author: ardalis
description: "了解如何使用应用程序部件，即 abstrations 对应用程序中的资源，来配置应用程序发现或避免从程序集加载功能。"
ms.author: riande
manager: wpickett
ms.date: 01/04/2017
ms.topic: article
ms.technology: aspnet
ms.prod: asp.net-core
uid: mvc/extensibility/app-parts
ms.openlocfilehash: 12c34b7a9521835533998c5609870bc712a6d48c
ms.sourcegitcommit: 3e303620a125325bb9abd4b2d315c106fb8c47fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="application-parts-in-aspnet-core"></a><span data-ttu-id="3a9ee-103">在 ASP.NET 核心中的应用程序部分</span><span class="sxs-lookup"><span data-stu-id="3a9ee-103">Application Parts in ASP.NET Core</span></span>

<span data-ttu-id="3a9ee-104">[查看或下载示例代码](https://github.com/aspnet/Docs/tree/master/aspnetcore/mvc/advanced/app-parts/sample)（[如何下载](xref:tutorials/index#how-to-download-a-sample)）</span><span class="sxs-lookup"><span data-stu-id="3a9ee-104">[View or download sample code](https://github.com/aspnet/Docs/tree/master/aspnetcore/mvc/advanced/app-parts/sample) ([how to download](xref:tutorials/index#how-to-download-a-sample))</span></span>

<span data-ttu-id="3a9ee-105">*应用程序部分*是上的应用程序，MVC 控制器，视图组件等从中的功能的资源的抽象或标记帮助程序可能被发现。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-105">An *Application Part* is an abstraction over the resources of an application, from which MVC features like controllers, view components, or tag helpers may be discovered.</span></span> <span data-ttu-id="3a9ee-106">应用程序一部分的一个示例是 AssemblyPart，封装程序集引用和公开类型和编译引用。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-106">One example of an application part is an AssemblyPart, which encapsulates an assembly reference and exposes types and compilation references.</span></span> <span data-ttu-id="3a9ee-107">*功能提供程序*适用于要填充的 ASP.NET 核心 MVC 应用程序的功能的应用程序部件。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-107">*Feature providers* work with application parts to populate the features of an ASP.NET Core MVC app.</span></span> <span data-ttu-id="3a9ee-108">应用程序部件的主要用例是允许你配置应用程序发现 （或避免加载） 从程序集的 MVC 功能。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-108">The main use case for application parts is to allow you to configure your app to discover (or avoid loading) MVC features from an assembly.</span></span>

## <a name="introducing-application-parts"></a><span data-ttu-id="3a9ee-109">引入应用程序部分</span><span class="sxs-lookup"><span data-stu-id="3a9ee-109">Introducing Application Parts</span></span>

<span data-ttu-id="3a9ee-110">MVC 应用程序加载从其功能[应用程序部件](/aspnet/core/api/microsoft.aspnetcore.mvc.applicationparts.applicationpart)。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-110">MVC apps load their features from [application parts](/aspnet/core/api/microsoft.aspnetcore.mvc.applicationparts.applicationpart).</span></span> <span data-ttu-id="3a9ee-111">具体而言， [AssemblyPart](/aspnet/core/api/microsoft.aspnetcore.mvc.applicationparts.assemblypart#Microsoft_AspNetCore_Mvc_ApplicationParts_AssemblyPart)类表示由程序集的应用程序部分。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-111">In particular, the [AssemblyPart](/aspnet/core/api/microsoft.aspnetcore.mvc.applicationparts.assemblypart#Microsoft_AspNetCore_Mvc_ApplicationParts_AssemblyPart) class represents an application part that is backed by an assembly.</span></span> <span data-ttu-id="3a9ee-112">可以使用这些类能够发现和加载 MVC 功能，例如控制器、 视图组件、 标记帮助程序和 razor 编译源。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-112">You can use these classes to discover and load MVC features, such as controllers, view components, tag helpers, and razor compilation sources.</span></span> <span data-ttu-id="3a9ee-113">[ApplicationPartManager](/aspnet/core/api/microsoft.aspnetcore.mvc.applicationparts.applicationpartmanager)负责跟踪对 MVC 应用程序的应用程序部件和可用功能提供程序。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-113">The [ApplicationPartManager](/aspnet/core/api/microsoft.aspnetcore.mvc.applicationparts.applicationpartmanager) is responsible for tracking the application parts and feature providers available to the MVC app.</span></span> <span data-ttu-id="3a9ee-114">你可以与交互`ApplicationPartManager`中`Startup`配置 MVC 时：</span><span class="sxs-lookup"><span data-stu-id="3a9ee-114">You can interact with the `ApplicationPartManager` in `Startup` when you configure MVC:</span></span>

```csharp
// create an assembly part from a class's assembly
var assembly = typeof(Startup).GetTypeInfo().Assembly;
services.AddMvc()
    .AddApplicationPart(assembly);

// OR
var assembly = typeof(Startup).GetTypeInfo().Assembly;
var part = new AssemblyPart(assembly);
services.AddMvc()
    .ConfigureApplicationPartManager(apm => p.ApplicationParts.Add(part));
```

<span data-ttu-id="3a9ee-115">默认情况下 MVC 将搜索依赖关系树并查找控制器 （即使其他程序集）。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-115">By default MVC will search the dependency tree and find controllers (even in other assemblies).</span></span> <span data-ttu-id="3a9ee-116">若要加载 （例如，来自不引用在编译时的插件） 的任意程序集，可以使用应用程序部分。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-116">To load an arbitrary assembly (for instance, from a plugin that isn't referenced at compile time), you can use an application part.</span></span>

<span data-ttu-id="3a9ee-117">你可以使用应用程序部分*避免*查找特定的程序集或位置中的控制器。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-117">You can use application parts to *avoid* looking for controllers in a particular assembly or location.</span></span> <span data-ttu-id="3a9ee-118">你可以控制哪些部分 （或程序集） 可以应用可通过修改`ApplicationParts`集合`ApplicationPartManager`。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-118">You can control which parts (or assemblies) are available to the app by modifying the `ApplicationParts` collection of the `ApplicationPartManager`.</span></span> <span data-ttu-id="3a9ee-119">中的项的顺序`ApplicationParts`集合并不重要。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-119">The order of the entries in the `ApplicationParts` collection is not important.</span></span> <span data-ttu-id="3a9ee-120">务必要完全配置`ApplicationPartManager`然后使用它来配置容器中的服务。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-120">It is important to fully configure the `ApplicationPartManager` before using it to configure services in the container.</span></span> <span data-ttu-id="3a9ee-121">例如，你应完全配置`ApplicationPartManager`之前调用`AddControllersAsServices`。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-121">For example, you should fully configure the `ApplicationPartManager` before invoking `AddControllersAsServices`.</span></span> <span data-ttu-id="3a9ee-122">未能这样做，请将意味着，应用程序部分中的控制器之后添加方法调用不会受到影响 （将不获取注册作为服务） 这可能导致不正确 bevavior 的你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-122">Failing to do so, will mean that controllers in application parts added after that method call will not be affected (will not get registered as services) which might result in incorrect bevavior of your application.</span></span>

<span data-ttu-id="3a9ee-123">如果你有该程序集包含不想要使用控制器，则将其从删除`ApplicationPartManager`:</span><span class="sxs-lookup"><span data-stu-id="3a9ee-123">If you have an assembly that contains controllers you do not want to be used, remove it from the `ApplicationPartManager`:</span></span>

```csharp
services.AddMvc()
    .ConfigureApplicationPartManager(p =>
    {
        var dependentLibrary = p.ApplicationParts
            .FirstOrDefault(part => part.Name == "DependentLibrary");

        if (dependentLibrary != null)
        {
           p.ApplicationParts.Remove(dependentLibrary);
        }
    })
```

<span data-ttu-id="3a9ee-124">除了你的项目的程序集和其依赖的程序集，`ApplicationPartManager`将包括的部件`Microsoft.AspNetCore.Mvc.TagHelpers`和`Microsoft.AspNetCore.Mvc.Razor`默认情况下。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-124">In addition to your project's assembly and its dependent assemblies, the `ApplicationPartManager` will include parts for `Microsoft.AspNetCore.Mvc.TagHelpers` and `Microsoft.AspNetCore.Mvc.Razor` by default.</span></span>

## <a name="application-feature-providers"></a><span data-ttu-id="3a9ee-125">应用程序功能提供程序</span><span class="sxs-lookup"><span data-stu-id="3a9ee-125">Application Feature Providers</span></span>

<span data-ttu-id="3a9ee-126">应用程序功能提供程序检查应用程序部分，并为那些部分中提供的功能。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-126">Application Feature Providers examine application parts and provide features for those parts.</span></span> <span data-ttu-id="3a9ee-127">有于以下 MVC 功能的内置功能提供程序：</span><span class="sxs-lookup"><span data-stu-id="3a9ee-127">There are built-in feature providers for the following MVC features:</span></span>

* [<span data-ttu-id="3a9ee-128">控制器</span><span class="sxs-lookup"><span data-stu-id="3a9ee-128">Controllers</span></span>](https://docs.microsoft.com/aspnet/core/api/microsoft.aspnetcore.mvc.controllers.controllerfeatureprovider)
* [<span data-ttu-id="3a9ee-129">元数据引用</span><span class="sxs-lookup"><span data-stu-id="3a9ee-129">Metadata Reference</span></span>](https://docs.microsoft.com/aspnet/core/api/microsoft.aspnetcore.mvc.razor.compilation.metadatareferencefeatureprovider)
* [<span data-ttu-id="3a9ee-130">标记帮助程序</span><span class="sxs-lookup"><span data-stu-id="3a9ee-130">Tag Helpers</span></span>](https://docs.microsoft.com/aspnet/core/api/microsoft.aspnetcore.mvc.razor.taghelpers.taghelperfeatureprovider)
* [<span data-ttu-id="3a9ee-131">查看组件</span><span class="sxs-lookup"><span data-stu-id="3a9ee-131">View Components</span></span>](https://docs.microsoft.com/aspnet/core/api/microsoft.aspnetcore.mvc.viewcomponents.viewcomponentfeatureprovider)

<span data-ttu-id="3a9ee-132">功能提供程序从继承`IApplicationFeatureProvider<T>`，其中`T`是一种功能。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-132">Feature providers inherit from `IApplicationFeatureProvider<T>`, where `T` is the type of the feature.</span></span> <span data-ttu-id="3a9ee-133">你可以实现你自己上面列出的任一 MVC 的特征类型提供程序的功能。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-133">You can implement your own feature providers for any of MVC's feature types listed above.</span></span> <span data-ttu-id="3a9ee-134">功能中的提供程序的顺序`ApplicationPartManager.FeatureProviders`集合可能很重要，因为更高版本的提供程序可以响应以前的提供程序执行操作。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-134">The order of feature providers in the `ApplicationPartManager.FeatureProviders` collection can be important, since later providers can react to actions taken by previous providers.</span></span>

### <a name="sample-generic-controller-feature"></a><span data-ttu-id="3a9ee-135">示例： 泛型控制器功能</span><span class="sxs-lookup"><span data-stu-id="3a9ee-135">Sample: Generic controller feature</span></span>

<span data-ttu-id="3a9ee-136">默认情况下，ASP.NET 核心 MVC 会忽略泛型控制器 (例如， `SomeController<T>`)。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-136">By default, ASP.NET Core MVC ignores generic controllers (for example, `SomeController<T>`).</span></span> <span data-ttu-id="3a9ee-137">此示例使用控制器的功能提供程序，在默认的提供程序后运行，并添加有关指定列表的类型的泛型控制器实例 (在中定义`EntityTypes.Types`):</span><span class="sxs-lookup"><span data-stu-id="3a9ee-137">This sample uses a controller feature provider that runs after the default provider and adds generic controller instances for a specified list of types (defined in `EntityTypes.Types`):</span></span>

[!code-csharp[Main](./app-parts/sample/AppPartsSample/GenericControllerFeatureProvider.cs?highlight=13&range=18-36)]

<span data-ttu-id="3a9ee-138">实体类型中：</span><span class="sxs-lookup"><span data-stu-id="3a9ee-138">The entity types:</span></span>

[!code-csharp[Main](./app-parts/sample/AppPartsSample/Model/EntityTypes.cs?range=6-16)]

<span data-ttu-id="3a9ee-139">在中添加功能提供程序`Startup`:</span><span class="sxs-lookup"><span data-stu-id="3a9ee-139">The feature provider is added in `Startup`:</span></span>

```csharp
services.AddMvc()
    .ConfigureApplicationPartManager(p => 
        p.FeatureProviders.Add(new GenericControllerFeatureProvider()));
```

<span data-ttu-id="3a9ee-140">默认情况下，用于路由的泛型控制器名称将在窗体*GenericController'1 [小组件]*而不是*小组件*。</span><span class="sxs-lookup"><span data-stu-id="3a9ee-140">By default, the generic controller names used for routing would be of the form *GenericController\`1[Widget]* instead of *Widget*.</span></span> <span data-ttu-id="3a9ee-141">以下属性用于修改要对应于控制器使用的泛型类型的名称：</span><span class="sxs-lookup"><span data-stu-id="3a9ee-141">The following attribute is used to modify the name to correspond to the generic type used by the controller:</span></span>

[!code-csharp[Main](./app-parts/sample/AppPartsSample/GenericControllerNameConvention.cs)]

<span data-ttu-id="3a9ee-142">`GenericController`类：</span><span class="sxs-lookup"><span data-stu-id="3a9ee-142">The `GenericController` class:</span></span>

[!code-csharp[Main](./app-parts/sample/AppPartsSample/GenericController.cs?highlight=5-6)]

<span data-ttu-id="3a9ee-143">这样，当请求匹配的路由：</span><span class="sxs-lookup"><span data-stu-id="3a9ee-143">The result, when a matching route is requested:</span></span>

![输出示例应用中的示例将读取，Hello from 泛型 Sproket 控制器。](app-parts/_static/generic-controller.png)

### <a name="sample-display-available-features"></a><span data-ttu-id="3a9ee-145">示例： 显示可用功能</span><span class="sxs-lookup"><span data-stu-id="3a9ee-145">Sample: Display available features</span></span>

<span data-ttu-id="3a9ee-146">你可循环访问提供的填充功能向应用程序通过请求`ApplicationPartManager`通过[依赖关系注入](../../fundamentals/dependency-injection.md)并使用它来填充相应功能的实例：</span><span class="sxs-lookup"><span data-stu-id="3a9ee-146">You can iterate through the populated features available to your app by requesting an `ApplicationPartManager` through [dependency injection](../../fundamentals/dependency-injection.md) and using it to populate instances of the appropriate features:</span></span>

[!code-csharp[Main](./app-parts/sample/AppPartsSample/Controllers/FeaturesController.cs?highlight=16,25-27)]

<span data-ttu-id="3a9ee-147">示例输出：</span><span class="sxs-lookup"><span data-stu-id="3a9ee-147">Example output:</span></span>

![示例应用中的示例输出](app-parts/_static/available-features.png)