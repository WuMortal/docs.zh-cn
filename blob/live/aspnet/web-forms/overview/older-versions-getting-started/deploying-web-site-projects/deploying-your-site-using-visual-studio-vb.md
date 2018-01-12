---
uid: web-forms/overview/older-versions-getting-started/deploying-web-site-projects/deploying-your-site-using-visual-studio-vb
title: "部署你的网站使用 Visual Studio (VB) |Microsoft 文档"
author: rick-anderson
description: "Visual Studio 包含用于部署网站工具。 在本教程中了解有关这些工具的详细信息。"
ms.author: aspnetcontent
manager: wpickett
ms.date: 04/01/2009
ms.topic: article
ms.assetid: 977105f3-7987-4e50-8be7-afb53b4ca28a
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /web-forms/overview/older-versions-getting-started/deploying-web-site-projects/deploying-your-site-using-visual-studio-vb
msc.type: authoredcontent
ms.openlocfilehash: af4257a91c08efc498c86aceac6fa7f64e527a74
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2017
---
<a name="deploying-your-site-using-visual-studio-vb"></a><span data-ttu-id="8ea4b-104">部署你的网站使用 Visual Studio (VB)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-104">Deploying Your Site Using Visual Studio (VB)</span></span>
====================
<span data-ttu-id="8ea4b-105">通过[Scott Mitchell](https://twitter.com/ScottOnWriting)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-105">by [Scott Mitchell](https://twitter.com/ScottOnWriting)</span></span>

<span data-ttu-id="8ea4b-106">[下载代码](http://download.microsoft.com/download/4/5/F/45F815EC-8B0E-46D3-9FB8-2DC015CCA306/ASPNET_Hosting_Tutorial_04_VB.zip)或[下载 PDF](http://download.microsoft.com/download/E/8/9/E8920AE6-D441-41A7-8A77-9EF8FF970D8B/aspnet_tutorial04_DeployingViaVS_vb.pdf)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-106">[Download Code](http://download.microsoft.com/download/4/5/F/45F815EC-8B0E-46D3-9FB8-2DC015CCA306/ASPNET_Hosting_Tutorial_04_VB.zip) or [Download PDF](http://download.microsoft.com/download/E/8/9/E8920AE6-D441-41A7-8A77-9EF8FF970D8B/aspnet_tutorial04_DeployingViaVS_vb.pdf)</span></span>

> <span data-ttu-id="8ea4b-107">Visual Studio 包含用于部署网站工具。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-107">Visual Studio includes tools for deploying a website.</span></span> <span data-ttu-id="8ea4b-108">在本教程中了解有关这些工具的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-108">Learn more about these tools in this tutorial.</span></span>


## <a name="introduction"></a><span data-ttu-id="8ea4b-109">介绍</span><span class="sxs-lookup"><span data-stu-id="8ea4b-109">Introduction</span></span>

<span data-ttu-id="8ea4b-110">前面的教程介绍了如何部署到 web 主机提供商的简单 ASP.NET web 应用。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-110">The preceding tutorial looked at how to deploy a simple ASP.NET web application to a web host provider.</span></span> <span data-ttu-id="8ea4b-111">具体而言，本教程说明了如何使用 FileZilla 等 FTP 客户端将从开发环境的所需的文件传输到生产环境。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-111">Specifically, the tutorial showed how to use an FTP client like FileZilla to transfer the necessary files from the development environment to the production environment.</span></span> <span data-ttu-id="8ea4b-112">Visual Studio 还提供内置的工具可简化部署到 web 主机提供商。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-112">Visual Studio also offers built-in tools to facilitate deployment to a web host provider.</span></span> <span data-ttu-id="8ea4b-113">本教程检查两个这些工具: 复制网站工具，其中你可以将文件移到和从远程 web 服务器使用 FTP 或 FrontPage 服务器扩展;和发布工具，将整个网站复制到指定位置。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-113">This tutorial examines two of these tools: the Copy Web Site tool, where you can move files to and from a remote web server using FTP or FrontPage Server Extensions; and the Publish tool, which copies the entire website to a specified location.</span></span>


> [!NOTE]
> <span data-ttu-id="8ea4b-114">由 Visual Studio 提供其他与部署相关的工具包括[Web 安装程序项目](https://msdn.microsoft.com/en-us/library/wx3b589t.aspx)和[Web 部署项目](https://www.microsoft.com/downloads/details.aspx?FamilyId=0AA30AE8-C73B-4BDD-BB1B-FE697256C459&amp;displaylang=en)外接程序。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-114">Other deployment-related tools offered by Visual Studio include [Web Setup Projects](https://msdn.microsoft.com/en-us/library/wx3b589t.aspx) and [Web Deployment Projects](https://www.microsoft.com/downloads/details.aspx?FamilyId=0AA30AE8-C73B-4BDD-BB1B-FE697256C459&amp;displaylang=en) Add-In.</span></span> <span data-ttu-id="8ea4b-115">Web 安装程序项目包网站的内容和配置信息导出成单一的 MSI 文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-115">Web Setup Projects package a website's contents and configuration information into a single MSI file.</span></span> <span data-ttu-id="8ea4b-116">此选项将在 intranet 内部署的网站或公司的销售的预打包的 web 应用程序在其自己的 web 服务器上安装客户最为有用。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-116">This option is most useful for websites that are deployed within an intranet or for companies that sell a pre-packaged web application that customers install on their own web servers.</span></span> <span data-ttu-id="8ea4b-117">Web 部署项目外接程序是 Visual Studio 外接程序，它方便了之间的指定配置差异生成用于开发环境和生产环境。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-117">The Web Deployment Projects Add-In is a Visual Studio Add-In that facilitates specifying configuration differences between builds for development environments and production environments.</span></span> <span data-ttu-id="8ea4b-118">本教程系列; 不讨论 web 安装程序项目Web 部署项目中总结了[*常见配置差异之间开发和生产*](common-configuration-differences-between-development-and-production-vb.md)教程。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-118">Web Setup Projects are not discussed in this tutorial series; Web Deployment Projects are summarized in the [*Common Configuration Differences Between Development and Production*](common-configuration-differences-between-development-and-production-vb.md) tutorial.</span></span>


## <a name="deploying-your-site-using-the-copy-web-site-tool"></a><span data-ttu-id="8ea4b-119">部署站点上使用复制网站工具</span><span class="sxs-lookup"><span data-stu-id="8ea4b-119">Deploying Your Site Using the Copy Web Site Tool</span></span>

<span data-ttu-id="8ea4b-120">Visual Studio 的复制网站工具是在功能上类似于独立的 FTP 客户端。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-120">Visual Studio's Copy Web Site tool is similar in functionality to a stand-alone FTP client.</span></span> <span data-ttu-id="8ea4b-121">简而言之，复制网站工具，可连接到远程网站通过 FTP 或 FrontPage 服务器扩展。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-121">In a nutshell, the Copy Web Site tool allows you to connect to a remote web site through FTP or FrontPage Server Extensions.</span></span> <span data-ttu-id="8ea4b-122">复制网站用户界面包含类似于 FileZilla 的用户界面，两个窗格： 左窗格中列出的本地文件，而右窗格中列出这些文件在目标服务器上的。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-122">Similar to FileZilla's user interface, the Copy Web Site user interface consists of two panes: the left pane lists the local files while the right pane lists those files on the destination server.</span></span>

> [!NOTE]
> <span data-ttu-id="8ea4b-123">复制网站工具仅适用于网站项目。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-123">The Copy Web Site tool is only available for Web Site Projects.</span></span> <span data-ttu-id="8ea4b-124">当您正在使用 Web 应用程序项目，visual Studio 确实提供此工具。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-124">Visual Studio does offer this tool when you are working with a Web Application Project.</span></span>


<span data-ttu-id="8ea4b-125">让我们看看使用复制网站工具发布到生产环境簿查看应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-125">Let's take a look at using the Copy Web Site tool to publish the Book Review application to production.</span></span> <span data-ttu-id="8ea4b-126">复制网站工具仅适用于使用的网站项目模型的项目，因为我们仅可以检查与 BookReviewsWSP 项目中使用此工具。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-126">Because the Copy Web Site tool only works with projects that use the Web Site Project model we can only examine using this tool with the BookReviewsWSP project.</span></span> <span data-ttu-id="8ea4b-127">打开该项目。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-127">Open that project.</span></span>

<span data-ttu-id="8ea4b-128">通过单击复制网站图标 （此图标圆形图 1 中） 的解决方案资源管理器; 启动复制网站工具项目或者，你可以从网站菜单上选择复制网站选项。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-128">Launch the Copy Web Site tool project by clicking the Copy Web Site icon in the Solution Explorer (this icon is circled in Figure 1); alternatively, you can select the Copy Web Site option from the Website menu.</span></span> <span data-ttu-id="8ea4b-129">这两种方法启动显示在图 1 中; 的复制网站用户界面图 1 中的，左窗格中仅被填充，因为我们尚未连接到远程服务器。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-129">Either approach launches the Copy Web Site user interface shown in Figure 1; only the left pane in Figure 1 is populated because we have yet to connect to a remote server.</span></span>


<span data-ttu-id="8ea4b-130">[![复制网站工具的用户界面是划分到两个窗格](deploying-your-site-using-visual-studio-vb/_static/image2.png)](deploying-your-site-using-visual-studio-vb/_static/image1.png)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-130">[![The Copy Web Site Tool's User Interface is Divided Into Two Panes](deploying-your-site-using-visual-studio-vb/_static/image2.png)](deploying-your-site-using-visual-studio-vb/_static/image1.png)</span></span>

<span data-ttu-id="8ea4b-131">**图 1**: 复制网站工具的用户界面是划分到两个窗格 ([单击以查看实际尺寸的图像](deploying-your-site-using-visual-studio-vb/_static/image3.png))</span><span class="sxs-lookup"><span data-stu-id="8ea4b-131">**Figure 1**: The Copy Web Site Tool's User Interface is Divided Into Two Panes ([Click to view full-size image](deploying-your-site-using-visual-studio-vb/_static/image3.png))</span></span>


<span data-ttu-id="8ea4b-132">若要部署我们的站点中，我们需要首先连接到 web 宿主提供程序。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-132">In order to deploy our site we need to first connect to the web host provider.</span></span> <span data-ttu-id="8ea4b-133">单击顶部的复制网站用户界面连接按钮。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-133">Click the Connect button at the top of the Copy Web Site user interface.</span></span> <span data-ttu-id="8ea4b-134">此时将显示打开网站对话框，在图 2 所示。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-134">This displays the Open Web Site dialog box shown in Figure 2.</span></span>

<span data-ttu-id="8ea4b-135">你可以通过从左侧选择四个选项之一来连接到目标网站：</span><span class="sxs-lookup"><span data-stu-id="8ea4b-135">You can connect to the destination website by selecting one of the four options from the left:</span></span>

- <span data-ttu-id="8ea4b-136">**文件系统**-选择此选项可从你的计算机将您的网站部署到可访问的文件夹或网络共享。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-136">**File System** - select this to deploy your site to a folder or network share accessible from your computer.</span></span>
- <span data-ttu-id="8ea4b-137">**本地 IIS** -使用此选项将站点部署到您的计算机上安装的 IIS web 服务器。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-137">**Local IIS** - use this option to deploy the site to the IIS web server installed on your computer.</span></span>
- <span data-ttu-id="8ea4b-138">**FTP 站点**-连接到远程网站使用 FTP。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-138">**FTP Site** - connect to a remote web site using FTP.</span></span>
- <span data-ttu-id="8ea4b-139">**远程站点**-连接到远程网站使用 FrontPage 服务器扩展。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-139">**Remote Site** - connect to a remote website using FrontPage Server Extensions.</span></span>

<span data-ttu-id="8ea4b-140">大多数 web 宿主提供程序支持 FTP，但更少提供 FrontPage 服务器扩展支持。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-140">Most web host providers support FTP, but fewer offer FrontPage Server Extension support.</span></span> <span data-ttu-id="8ea4b-141">为此，我已选择了 FTP 站点的选项，然后输入连接信息，如图 2 中所示。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-141">For that reason, I've selected the FTP Site option and then entered the connection information as shown in Figure 2.</span></span>


<span data-ttu-id="8ea4b-142">[![指定目标网站](deploying-your-site-using-visual-studio-vb/_static/image5.png)](deploying-your-site-using-visual-studio-vb/_static/image4.png)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-142">[![Specify the Destination Website](deploying-your-site-using-visual-studio-vb/_static/image5.png)](deploying-your-site-using-visual-studio-vb/_static/image4.png)</span></span>

<span data-ttu-id="8ea4b-143">**图 2**： 指定目标网站 ([单击以查看实际尺寸的图像](deploying-your-site-using-visual-studio-vb/_static/image6.png))</span><span class="sxs-lookup"><span data-stu-id="8ea4b-143">**Figure 2**: Specify the Destination Website ([Click to view full-size image](deploying-your-site-using-visual-studio-vb/_static/image6.png))</span></span>


<span data-ttu-id="8ea4b-144">连接后，复制网站工具加载在右窗格中的远程站点文件，并指示每个文件的状态： 新的、 已删除、 已更改或未更改。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-144">After you connect, the Copy Web Site tool loads the files at the remote site in the right pane and indicates the status of each file: New, Deleted, Changed, or Unchanged.</span></span> <span data-ttu-id="8ea4b-145">你可以将文件从本地站点复制到远程站点或进行相反的操作。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-145">You can copy a file from the local site to the remote site, or vice-a-versa.</span></span>

<span data-ttu-id="8ea4b-146">让我们添加一个新页到 BookReviewsWSP 项目，然后将其部署，以便我们可以看到操作中的复制网站工具。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-146">Let's add a new page to the BookReviewsWSP project and then deploy it so that we can see the Copy Web Site tool in action.</span></span> <span data-ttu-id="8ea4b-147">Visual Studio 中名为的根目录中创建新的 ASP.NET 页`Privacy.aspx`。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-147">Create a new ASP.NET page in Visual Studio in the root directory named `Privacy.aspx`.</span></span> <span data-ttu-id="8ea4b-148">使用母版页页面`Site.master`并将站点的隐私策略添加到此页。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-148">Have the page use the master page `Site.master` and add your site's privacy policy to this page.</span></span> <span data-ttu-id="8ea4b-149">创建此页后，图 3 显示 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-149">Figure 3 shows Visual Studio after this page has been created.</span></span>


<span data-ttu-id="8ea4b-150">[![添加新的页名为&lt;代码&gt;Privacy.aspx&lt;/c o&gt;到网站的根文件夹](deploying-your-site-using-visual-studio-vb/_static/image8.png)](deploying-your-site-using-visual-studio-vb/_static/image7.png)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-150">[![Add a New Page Named &lt;code&gt;Privacy.aspx&lt;/code&gt; to the Website's Root Folder](deploying-your-site-using-visual-studio-vb/_static/image8.png)](deploying-your-site-using-visual-studio-vb/_static/image7.png)</span></span>

<span data-ttu-id="8ea4b-151">**图 3**： 添加新的页名为`Privacy.aspx`到网站的根文件夹 ([单击以查看实际尺寸的图像](deploying-your-site-using-visual-studio-vb/_static/image9.png))</span><span class="sxs-lookup"><span data-stu-id="8ea4b-151">**Figure 3**: Add a New Page Named `Privacy.aspx` to the Website's Root Folder ([Click to view full-size image](deploying-your-site-using-visual-studio-vb/_static/image9.png))</span></span>


<span data-ttu-id="8ea4b-152">接下来，返回到复制网站用户界面。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-152">Next, return to the Copy Web Site user interface.</span></span> <span data-ttu-id="8ea4b-153">如图 4 所示，左窗格中现在包含新的文件-`Policy.aspx`和`Policy.aspx.vb`。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-153">As Figure 4 shows, the left pane now includes the new files - `Policy.aspx` and `Policy.aspx.vb`.</span></span> <span data-ttu-id="8ea4b-154">更重要的是，这些文件都标有一个箭头图标和一个状态的新的该值指示它们存在本地站点上但不是能在远程站点。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-154">What's more, these files are marked with an arrow icon and a Status of New, indicating that they exist on the local site but not on the remote site.</span></span>


<span data-ttu-id="8ea4b-155">[![复制网站工具包括新建&lt;代码&gt;Privacy.aspx&lt;/c o&gt;在其左侧窗格中的页](deploying-your-site-using-visual-studio-vb/_static/image11.png)](deploying-your-site-using-visual-studio-vb/_static/image10.png)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-155">[![The Copy Web Site Tool Includes the New &lt;code&gt;Privacy.aspx&lt;/code&gt; Page in its Left Pane](deploying-your-site-using-visual-studio-vb/_static/image11.png)](deploying-your-site-using-visual-studio-vb/_static/image10.png)</span></span>

<span data-ttu-id="8ea4b-156">**图 4**： 复制网站工具包括新建`Privacy.aspx`在其左侧窗格中的页 ([单击以查看实际尺寸的图像](deploying-your-site-using-visual-studio-vb/_static/image12.png))</span><span class="sxs-lookup"><span data-stu-id="8ea4b-156">**Figure 4**: The Copy Web Site Tool Includes the New `Privacy.aspx` Page in its Left Pane ([Click to view full-size image](deploying-your-site-using-visual-studio-vb/_static/image12.png))</span></span>


<span data-ttu-id="8ea4b-157">若要部署新文件选择它们，然后单击箭头图标，以将它们传输到远程站点。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-157">To deploy the new files select them and then click the arrow icon to transfer them to the remote site.</span></span> <span data-ttu-id="8ea4b-158">传输完成后`Policy.aspx`和`Policy.aspx.vb`文件存在于状态未更改与本地和远程站点上。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-158">After the transfer completes the `Policy.aspx` and `Policy.aspx.vb` files exist on both the local and remote sites with the status Unchanged.</span></span>

<span data-ttu-id="8ea4b-159">列出新的文件，以及复制网站工具突出显示了与不同，在本地和远程站点之间的任何文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-159">Along with listing new files, the Copy Web Site tool highlights any files that differ between the local and remote sites.</span></span> <span data-ttu-id="8ea4b-160">若要在操作中查看，请返回到`Privacy.aspx`页上，并将几个更多字添加到的隐私策略。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-160">To see this in action, return to the `Privacy.aspx` page and add a few more words to the privacy policy.</span></span> <span data-ttu-id="8ea4b-161">保存页，然后返回到复制网站工具。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-161">Save the page and then return to the Copy Web Site tool.</span></span> <span data-ttu-id="8ea4b-162">如图 5 所示，`Privacy.aspx`页的左窗格中的状态为已更改，该值指示它为与远程站点不同步。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-162">As Figure 5 shows, the `Privacy.aspx` page in the left pane has a status of Changed indicating that it is out of sync with the remote site.</span></span>


<span data-ttu-id="8ea4b-163">[![复制网站工具指示&lt;代码&gt;Privacy.aspx&lt;/c o&gt;页已更改](deploying-your-site-using-visual-studio-vb/_static/image14.png)](deploying-your-site-using-visual-studio-vb/_static/image13.png)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-163">[![The Copy Web Site Tool Indicates that the &lt;code&gt;Privacy.aspx&lt;/code&gt; Page has been Changed](deploying-your-site-using-visual-studio-vb/_static/image14.png)](deploying-your-site-using-visual-studio-vb/_static/image13.png)</span></span>

<span data-ttu-id="8ea4b-164">**图 5**： 复制网站工具指示`Privacy.aspx`页已更改 ([单击以查看实际尺寸的图像](deploying-your-site-using-visual-studio-vb/_static/image15.png))</span><span class="sxs-lookup"><span data-stu-id="8ea4b-164">**Figure 5**: The Copy Web Site Tool Indicates that the `Privacy.aspx` Page has been Changed ([Click to view full-size image](deploying-your-site-using-visual-studio-vb/_static/image15.png))</span></span>


<span data-ttu-id="8ea4b-165">复制网站工具还指示自上次复制操作以来是否已删除文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-165">The Copy Web Site tool also indicates if a file has been deleted since the last copy operation.</span></span> <span data-ttu-id="8ea4b-166">删除`Privacy.aspx`从本地项目并刷新复制网站工具。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-166">Delete the `Privacy.aspx` from the local project and refresh the Copy Web Site tool.</span></span> <span data-ttu-id="8ea4b-167">`Privacy.aspx`和`Privacy.aspx.vb`文件保持在左窗格中，列出，但具有，该值指示是否已将其删除自上次复制操作的状态为已删除。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-167">The `Privacy.aspx` and `Privacy.aspx.vb` files remain listed in the left pane, but have a Deleted status indicating that they have been removed since the last copy operation.</span></span>

## <a name="publishing-a-web-application"></a><span data-ttu-id="8ea4b-168">发布 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="8ea4b-168">Publishing a Web Application</span></span>

<span data-ttu-id="8ea4b-169">部署 web 应用程序从 Visual Studio 中的另一种方法是使用发布选项，这是可通过生成菜单访问。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-169">Another way to deploy your web application from within Visual Studio is to use the Publish option, which is accessible via the Build menu.</span></span> <span data-ttu-id="8ea4b-170">发布选项显式编译应用程序，然后复制到指定的远程站点所需的文件的所有。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-170">The Publish option explicitly compiles the application and then copies all of the necessary files up to the specified remote site.</span></span> <span data-ttu-id="8ea4b-171">正如我们很快将看到的则发布选项是更钝比复制网站工具。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-171">As we'll see shortly, the Publish option is more blunt than the Copy Web Site tool.</span></span> <span data-ttu-id="8ea4b-172">复制网站工具，可以检查本地和远程站点上的文件，并允许您上载或下载单个文件，根据需要而发布选项部署整个 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-172">Whereas the Copy Web Site tool lets you examine the files on the local and remote sites and permits you to upload or download individual files as needed, the Publish option deploys the entire web application.</span></span>


<span data-ttu-id="8ea4b-173">除了将所有所需的文件复制到指定的远程站点，发布选项还可以显式编译应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-173">In addition to copying all of the needed files to the specified remote site, the Publish option also explicitly compiles the application.</span></span> <span data-ttu-id="8ea4b-174">假设 Web 应用程序项目只需要显式编译它应该为不足为奇了发布选项适用于 Web 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-174">Given that Web Application Projects need to be explicitly compiled it should come as no surprise that the Publish option is available for Web Application Projects.</span></span> <span data-ttu-id="8ea4b-175">新增功能可能有点令人惊讶是发布选项也是适用于网站项目。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-175">What may be a bit surprising is that the Publish option is also available for Web Site Projects.</span></span> <span data-ttu-id="8ea4b-176">中所述[*确定什么文件需要部署到*](determining-what-files-need-to-be-deployed-vb.md)教程中，网站项目显式编译完成的过程称为*预编译*。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-176">As noted in the [*Determining What Files Need to Be Deployed*](determining-what-files-need-to-be-deployed-vb.md) tutorial, Web Site Projects can be explicitly compiled through a process referred to as *pre-compilation*.</span></span> <span data-ttu-id="8ea4b-177">本教程侧重于与 Web 应用程序项目; 使用发布选项将来的教程将探索如何预编译，此时我们将返回以查看使用的网站项目的发布选项。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-177">This tutorial focuses on using the Publish option with Web Application Projects; a future tutorial will explore pre-compilation, at which point we'll return to look at using the Publish option with Web Site Projects.</span></span>

> [!NOTE]
> <span data-ttu-id="8ea4b-178">对于网站项目和 Web 应用程序项目的 Visual Studio 中提供的发布选项时，Visual Web Developer 仅提供 Web 应用程序项目的发布选项。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-178">While the Publish option is available in Visual Studio for both Web Site Projects and Web Application Projects, Visual Web Developer only offers the Publish option for Web Application Projects.</span></span>


<span data-ttu-id="8ea4b-179">让我们看一下部署簿评审应用程序使用发布选项。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-179">Let's look at deploying the Book Reviews application using the Publish option.</span></span> <span data-ttu-id="8ea4b-180">首先在 Visual Studio 中打开 BookReviewsWAP （Web 应用程序项目）。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-180">Start by opening BookReviewsWAP (the Web Application Project) in Visual Studio.</span></span> <span data-ttu-id="8ea4b-181">从发布菜单上选择生成 BookReviewsWAP 项目。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-181">From the Publish menu choose the Build BookReviewsWAP project.</span></span> <span data-ttu-id="8ea4b-182">这会打开一个对话框，提示输入目标位置，在其他配置选项中 （请参阅图 6）。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-182">This brings up a dialog box that prompts for the target location, among other configuration options (see Figure 6).</span></span> <span data-ttu-id="8ea4b-183">更像使用复制网站工具可以输入指向本地文件夹，在 IIS 上的本地网站，支持的 FrontPage 服务器扩展或 FTP 服务器地址的远程网站的位置。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-183">Much like with the Copy Web Site tool you can enter a location that points to a local folder, a local website on IIS, a remote website that supports FrontPage Server Extensions, or an FTP server address.</span></span> <span data-ttu-id="8ea4b-184">你可以选择是否要替换的已部署的文件的远程 web 服务器上的文件，或删除所有在发布前远程站点上的内容。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-184">You can choose whether to replace the files on the remote web server with the deployed files or to delete all of the content on the remote site before publishing.</span></span> <span data-ttu-id="8ea4b-185">你还可以指定是否将复制：</span><span class="sxs-lookup"><span data-stu-id="8ea4b-185">You can also specify whether to copy:</span></span>

- <span data-ttu-id="8ea4b-186">仅在项目中运行应用程序，它将省略不需要的源代码和与项目相关的文件所需文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-186">Only the files in the project needed to run the application, which omits the unneeded source code and project-related files.</span></span>
- <span data-ttu-id="8ea4b-187">所有项目文件，其中包括源代码文件和 Visual Studio 项目文件，都如解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-187">All project files, which includes the source code files and Visual Studio project files like the Solution file.</span></span>
- <span data-ttu-id="8ea4b-188">在源项目文件夹中，将所有文件都复制而不考虑是否要包括在项目中的源项目文件夹中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-188">All files in the source project folder, which copies all files in the source project folder regardless of whether they're included in the project.</span></span>

<span data-ttu-id="8ea4b-189">此外还有一个选项以将内容上载`App_Data`文件夹。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-189">There's also an option to upload the contents of the `App_Data` folder.</span></span>


<span data-ttu-id="8ea4b-190">[![指定目标网站](deploying-your-site-using-visual-studio-vb/_static/image17.png)](deploying-your-site-using-visual-studio-vb/_static/image16.png)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-190">[![Specify the Destination Website](deploying-your-site-using-visual-studio-vb/_static/image17.png)](deploying-your-site-using-visual-studio-vb/_static/image16.png)</span></span>

<span data-ttu-id="8ea4b-191">**图 6**： 指定目标网站 ([单击以查看实际尺寸的图像](deploying-your-site-using-visual-studio-vb/_static/image18.png))</span><span class="sxs-lookup"><span data-stu-id="8ea4b-191">**Figure 6**: Specify the Destination Website ([Click to view full-size image](deploying-your-site-using-visual-studio-vb/_static/image18.png))</span></span>


<span data-ttu-id="8ea4b-192">对于簿查看应用程序远程站点包含复制通过复制网站工具 BookReviewsWSP 项目时，部署的文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-192">For the Book Review application the remote site contains the files deployed when copying the BookReviewsWSP project via the Copy Web Site tool.</span></span> <span data-ttu-id="8ea4b-193">因此，让我们首先删除所有现有内容的发布选项。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-193">Therefore, let's have the Publish option start by deleting all existing content.</span></span> <span data-ttu-id="8ea4b-194">此外，让我们只复制所需的文件，而不是使用不需要的代码和项目源文件塞满生产环境。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-194">Also, let's just copy the necessary files rather than cluttering the production environment with unneeded source code and project files.</span></span> <span data-ttu-id="8ea4b-195">指定这些选项后, 单击发布按钮。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-195">After specifying these options, click the Publish button.</span></span> <span data-ttu-id="8ea4b-196">接下来的几秒内通过 Visual Studio 会将部署所需的文件到目标站点中，在输出窗口中显示其进度。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-196">Over the next several seconds Visual Studio will deploy the necessary files to the destination site, displaying its progress in the Output window.</span></span>

<span data-ttu-id="8ea4b-197">发布操作完成后，图 7 显示 FTP 站点上的文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-197">Figure 7 shows the files on the FTP site after the Publish operation has completed.</span></span> <span data-ttu-id="8ea4b-198">请注意，已上载仅的标记页面，并且需要服务器端和客户端的支持文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-198">Note that only the markup pages and the necessary sever- and client-side support files have been uploaded.</span></span>


<span data-ttu-id="8ea4b-199">[![仅将所需的文件发布到生产环境](deploying-your-site-using-visual-studio-vb/_static/image20.png)](deploying-your-site-using-visual-studio-vb/_static/image19.png)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-199">[![Only the Needed Files Were Published to the Production Environment](deploying-your-site-using-visual-studio-vb/_static/image20.png)](deploying-your-site-using-visual-studio-vb/_static/image19.png)</span></span>

<span data-ttu-id="8ea4b-200">**图 7**： 仅所需文件发布到生产环境 ([单击以查看实际尺寸的图像](deploying-your-site-using-visual-studio-vb/_static/image21.png))</span><span class="sxs-lookup"><span data-stu-id="8ea4b-200">**Figure 7**: Only the Needed Files Were Published to the Production Environment ([Click to view full-size image](deploying-your-site-using-visual-studio-vb/_static/image21.png))</span></span>


<span data-ttu-id="8ea4b-201">发布选项是比复制网站工具的较低一些略有区别的工具。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-201">The Publish option is a less nuanced tool than the Copy Web Site tool.</span></span> <span data-ttu-id="8ea4b-202">复制网站工具允许你检查本地和远程站点上的文件并查看它们有何不同，而发布选项提供了任何此类接口。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-202">Whereas the Copy Web Site tool allows you to inspect the files on the local and remote sites and see how they differ, the Publish option provides no such interface.</span></span> <span data-ttu-id="8ea4b-203">此外，该复制网站工具使您能够一次性更改，上载或删除单个文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-203">Moreover, the Copy Web Site tool enables you to make one-off changes, uploading or deleting individual files.</span></span> <span data-ttu-id="8ea4b-204">发布选项不允许此类细化的控制;相反，它将发布*整个*应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-204">The Publish option does not allow such fine-grained control; instead, it publishes the *entire* application.</span></span> <span data-ttu-id="8ea4b-205">此行为有其优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-205">This behavior has its pros and cons.</span></span> <span data-ttu-id="8ea4b-206">在加上一侧，你了解何时使用你不会忘记上载重要文件发布选项。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-206">On the plus side, you know when using the Publish option you won't be forgetting to upload an important file.</span></span> <span data-ttu-id="8ea4b-207">但考虑如果进行少量更改到非常大的网站-使用发布选项无法更新该页面或两个已修改，但必须等待尽管 Visual Studio 部署的整个站点，而是会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-207">But consider what happens if you have made a small change to a very large website - with the Publish option you cannot update that page or two that has been modified, but instead you must wait while Visual Studio deploys the entire site.</span></span>

<span data-ttu-id="8ea4b-208">并不少见，才会生产和开发环境之间不同，其内容的某些文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-208">It's not uncommon for there to be certain files whose content differs between the production and development environments.</span></span> <span data-ttu-id="8ea4b-209">重要的例子就是应用程序的配置文件， `Web.config`。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-209">A key example is the application's configuration file, `Web.config`.</span></span> <span data-ttu-id="8ea4b-210">因为发布选项会盲目地将复制的 web 应用程序文件时，它将与在开发环境中的版本覆盖生产环境中的自定义的配置文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-210">Because the Publish option blindly copies the web application files it overwrites the production environment's customized configuration files with the version in the development environment.</span></span> <span data-ttu-id="8ea4b-211">后续教程探讨此主题会进一步，并提供用于部署的 web 应用，这种差异存在时的提示。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-211">The subsequent tutorial explores this topic further and offers tips for deploying a web application when such differences exist.</span></span>

## <a name="summary"></a><span data-ttu-id="8ea4b-212">摘要</span><span class="sxs-lookup"><span data-stu-id="8ea4b-212">Summary</span></span>

<span data-ttu-id="8ea4b-213">将网站部署涉及将从开发环境的所需的文件复制到生产环境。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-213">Deploying a website involves copying the necessary files from the development environment to the production environment.</span></span> <span data-ttu-id="8ea4b-214">前面的教程介绍了如何使用 FileZilla 等 FTP 客户端传输文件。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-214">The previous tutorial showed how to transfer files using an FTP client like FileZilla.</span></span> <span data-ttu-id="8ea4b-215">本教程检查 Visual Studio 中的两个部署工具: 复制网站工具和发布选项。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-215">This tutorial examined two deployment tools in Visual Studio: the Copy Web Site tool and the Publish option.</span></span> <span data-ttu-id="8ea4b-216">它列出本地计算机和可以轻松地上载或下载两台计算机之间的文件的指定远程计算机上的文件的双窗格界面，该复制网站工具是类似于 FTP 客户端。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-216">The Copy Web Site tool is similar to an FTP client in that it has a two-paned interface listing the files on the local computer and a specified remote computer that makes it easy to upload or download files between the two computers.</span></span> <span data-ttu-id="8ea4b-217">发布选项是一个更钝工具显式将编译该项目，然后再部署到指定目标整个应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ea4b-217">The Publish option is a more blunt tool that explicitly compiles the project and then deploys the entire application to the specified destination.</span></span>

<span data-ttu-id="8ea4b-218">尽情享受编程 ！</span><span class="sxs-lookup"><span data-stu-id="8ea4b-218">Happy Programming!</span></span>

### <a name="further-reading"></a><span data-ttu-id="8ea4b-219">其他阅读材料</span><span class="sxs-lookup"><span data-stu-id="8ea4b-219">Further Reading</span></span>

<span data-ttu-id="8ea4b-220">在本教程中讨论的主题的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="8ea4b-220">For more information on the topics discussed in this tutorial, refer to the following resources:</span></span>

- [<span data-ttu-id="8ea4b-221">复制使用复制网站工具创建网站</span><span class="sxs-lookup"><span data-stu-id="8ea4b-221">Copying Web Site with the Copy Web Site Tool</span></span>](https://msdn.microsoft.com/en-us/library/1cc82atw.aspx)
- <span data-ttu-id="8ea4b-222">[I： 如何部署使用复制网站工具网站](../../../videos/how-do-i/how-do-i-deploy-a-web-site-using-the-copy-web-site-tool.md)（视频）</span><span class="sxs-lookup"><span data-stu-id="8ea4b-222">[How Do I: Deploy a Web Site Using the Copy Web Site Tool](../../../videos/how-do-i/how-do-i-deploy-a-web-site-using-the-copy-web-site-tool.md) (Video)</span></span>
- [<span data-ttu-id="8ea4b-223">如何： 发布 Web 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="8ea4b-223">How To: Publish Web Application Projects</span></span>](https://msdn.microsoft.com/en-us/library/aa983453.aspx)
- [<span data-ttu-id="8ea4b-224">如何： 发布网站</span><span class="sxs-lookup"><span data-stu-id="8ea4b-224">How To: Publish Web Sites</span></span>](https://msdn.microsoft.com/en-us/library/20yh9f1b.aspx)
- [<span data-ttu-id="8ea4b-225">安装程序和 Visual Studio 中的部署项目</span><span class="sxs-lookup"><span data-stu-id="8ea4b-225">Setup and Deployment Projects in Visual Studio</span></span>](https://msdn.microsoft.com/en-us/library/wx3b589t.aspx)

>[!div class="step-by-step"]
<span data-ttu-id="8ea4b-226">[上一页](deploying-your-site-using-an-ftp-client-vb.md)
[下一页](common-configuration-differences-between-development-and-production-vb.md)</span><span class="sxs-lookup"><span data-stu-id="8ea4b-226">[Previous](deploying-your-site-using-an-ftp-client-vb.md)
[Next](common-configuration-differences-between-development-and-production-vb.md)</span></span>