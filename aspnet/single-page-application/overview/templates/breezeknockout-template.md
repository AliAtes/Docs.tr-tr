---
uid: single-page-application/overview/templates/breezeknockout-template
title: "Kolay/Boşaltılan şablon | Microsoft Docs"
author: madskristensen
description: "Kolay/Boşaltılan tek sayfa uygulaması şablonu"
ms.author: aspnetcontent
manager: wpickett
ms.date: 01/30/2013
ms.topic: article
ms.assetid: 3bd94827-3c59-448f-abc3-36e6df4858db
ms.technology: 
ms.prod: .net-framework
msc.legacyurl: /single-page-application/overview/templates/breezeknockout-template
msc.type: authoredcontent
ms.openlocfilehash: 07ec099a0381458fe42c1972a2554f76fd34638c
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2017
---
<a name="breezeknockout-template"></a><span data-ttu-id="5a76e-103">Kolay/Boşaltılan şablonu</span><span class="sxs-lookup"><span data-stu-id="5a76e-103">Breeze/Knockout template</span></span>
====================
<span data-ttu-id="5a76e-104">tarafından [Kristensen Mads](https://github.com/madskristensen)</span><span class="sxs-lookup"><span data-stu-id="5a76e-104">by [Mads Kristensen](https://github.com/madskristensen)</span></span>

> <span data-ttu-id="5a76e-105">Kolay/Boşaltılan MVC şablonu tarafından Atla zil yazıldı</span><span class="sxs-lookup"><span data-stu-id="5a76e-105">The Breeze/Knockout MVC Template was written by Ward Bell</span></span>
> 
> [<span data-ttu-id="5a76e-106">Kolay/Boşaltılan MVC şablonu indirme</span><span class="sxs-lookup"><span data-stu-id="5a76e-106">Download the Breeze/Knockout MVC Template</span></span>](https://go.microsoft.com/fwlink/?LinkId=282649)


<span data-ttu-id="5a76e-107">"Tek sayfa uygulamasının" duymadığınız (SPA) ve ne olduğunu hiç merak ettiniz.</span><span class="sxs-lookup"><span data-stu-id="5a76e-107">You've heard of "single page application" (SPA) and wondered what it is.</span></span> <span data-ttu-id="5a76e-108">Bu konuda okuyabilir, ancak, yerine onu yaşamak için.</span><span class="sxs-lookup"><span data-stu-id="5a76e-108">While you could read about it, you'd rather experience it for yourself.</span></span> <span data-ttu-id="5a76e-109">Ancak bir örnek yükleme süresi olanların?</span><span class="sxs-lookup"><span data-stu-id="5a76e-109">But who has time to download a sample?</span></span> <span data-ttu-id="5a76e-110">Visual Studio ekranınız varsa, örneği SPA gerekir ve içinde değerinden 60 çalıştıran ile ASP.NET MVC 4 "Kolay/Boşaltılan tek sayfa uygulaması" şablonu saniye.</span><span class="sxs-lookup"><span data-stu-id="5a76e-110">If you've got Visual Studio, you'll have an example SPA up and running in less than 60 seconds with the ASP.NET MVC 4 "Breeze/Knockout Single Page Application" template.</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/ZephyrRunning.png)

## <a name="what-is-the-breezeknockout-spa-template"></a><span data-ttu-id="5a76e-111">Kolay/Boşaltılan SPA şablonu nedir?</span><span class="sxs-lookup"><span data-stu-id="5a76e-111">What is the Breeze/Knockout SPA Template?</span></span>

<span data-ttu-id="5a76e-112">Çoğu proje şablonları bir uygulama çatıyı oluşturur.</span><span class="sxs-lookup"><span data-stu-id="5a76e-112">Most project templates generate an application skeleton.</span></span> <span data-ttu-id="5a76e-113">Kodunuzu ekleyerek bu kemikler üzerinde flesh yerleştirin ve sonunda çalışan bir uygulama sunmak.</span><span class="sxs-lookup"><span data-stu-id="5a76e-113">You put flesh on those bones by adding your code and eventually deliver a working application.</span></span> <span data-ttu-id="5a76e-114">Kolay/Boşaltılan SPA şablon farklıdır.</span><span class="sxs-lookup"><span data-stu-id="5a76e-114">The Breeze/Knockout SPA template is different.</span></span> <span data-ttu-id="5a76e-115">Araştırmak örnek bir uygulama oluşturur.</span><span class="sxs-lookup"><span data-stu-id="5a76e-115">It generates a sample application for you to study.</span></span> <span data-ttu-id="5a76e-116">SPA uygulama tasarımı ve bir SPA oluşturmak için kullanılan teknikleri çoğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="5a76e-116">It demonstrates a SPA application design and many of the techniques for building a SPA.</span></span>

<span data-ttu-id="5a76e-117">Bir değişim açıktır kolay/Boşaltılan şablonu [Çakıştırmaları SPA şablonu](../introduction/knockoutjs-template.md) ASP.NET ve Web Araçları 2012.2 güncelleştirmesi dahil.</span><span class="sxs-lookup"><span data-stu-id="5a76e-117">The Breeze/Knockout template is a variation on the [KnockoutJS SPA template](../introduction/knockoutjs-template.md) included in the ASP.NET and Web Tools 2012.2 Update.</span></span> <span data-ttu-id="5a76e-118">Aynı kullanıcı deneyimini uygulamayla kolay SPA şablon oluşturur, ancak veri yönetimi için kolay kullanarak farklı bir uygulama bulunur.</span><span class="sxs-lookup"><span data-stu-id="5a76e-118">The Breeze SPA template generates an application with the same user experience, but it has a different implementation, using Breeze for data management.</span></span>

<span data-ttu-id="5a76e-119">Çakıştırmaları SPA şablon, basit bir uygulama için yeterli olduğu ham jQuery AJAX, olan hizmet istekleri hale getirir.</span><span class="sxs-lookup"><span data-stu-id="5a76e-119">The KnockoutJS SPA template makes service requests with raw jQuery AJAX, which is adequate for a simple application.</span></span> <span data-ttu-id="5a76e-120">Ancak daha karmaşık uygulamalar gittikçe veri yönetim gereksinimleri vardır.</span><span class="sxs-lookup"><span data-stu-id="5a76e-120">But more sophisticated apps have more demanding data management requirements.</span></span> <span data-ttu-id="5a76e-121">Örneğin, çoğu uygulamalar:</span><span class="sxs-lookup"><span data-stu-id="5a76e-121">For example, most applications:</span></span>

- <span data-ttu-id="5a76e-122">Sorgulamak ve sunucunun genişletilmiş kullanıcı oturumu sırasında yeniden sorgular.</span><span class="sxs-lookup"><span data-stu-id="5a76e-122">Query and re-query the server during an extended user session.</span></span>
- <span data-ttu-id="5a76e-123">Sıralama ve disk belleği sorgu filtreleri ekleyin.</span><span class="sxs-lookup"><span data-stu-id="5a76e-123">Add query filters, sorting, and paging.</span></span>
- <span data-ttu-id="5a76e-124">Aynı verileri birden çok ekranları arasında paylaşın.</span><span class="sxs-lookup"><span data-stu-id="5a76e-124">Share the same data across multiple screens.</span></span>
- <span data-ttu-id="5a76e-125">Birçok nesnelerdeki değişiklikleri accumulate, sonra bunları tek bir işlem olarak kaydedin.</span><span class="sxs-lookup"><span data-stu-id="5a76e-125">Accumulate changes to many objects, then save them as a single transaction.</span></span>
- <span data-ttu-id="5a76e-126">Kullanıcı veritabanına değişiklikleri kaydetmeden önce hataları düzeltmek için istemcideki değişikliklerin doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="5a76e-126">Validate changes on the client, so the user can correct mistakes before committing changes to the database.</span></span>

<span data-ttu-id="5a76e-127">BreezeJS kitaplığı bu, sizin için en önemli uygulama mantığı ve kullanıcı deneyimini geliştirmek için boşaltma işler.</span><span class="sxs-lookup"><span data-stu-id="5a76e-127">The BreezeJS library handles these chores for you, freeing you to develop the application logic and user experience that matter most.</span></span>

<span data-ttu-id="5a76e-128">[**Kolay** ](http://www.breezejs.com/?utm_source=ms-spa) JavaScript ve HTML, geçmişte tek başına Masaüstü uygulamaları teslim uygulamaları türlerini zengin veri uygulamaları oluşturmak için bir açık kaynak kitaplığı.</span><span class="sxs-lookup"><span data-stu-id="5a76e-128">[**Breeze**](http://www.breezejs.com/?utm_source=ms-spa) is an open source library for building rich data applications in JavaScript and HTML, the kinds of apps that have historically been delivered as stand-alone desktop applications.</span></span>

<span data-ttu-id="5a76e-129">Kolay/Boşaltılan şablonu daha güçlü bir veri yönetimi altyapı ilk bu önemli adım almanıza yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="5a76e-129">The Breeze/Knockout template helps you take that first crucial step toward a more robust data management infrastructure.</span></span> <span data-ttu-id="5a76e-130">Çakıştırmaları SPA şablona outwardly aynı olan bir örnek Todo uygulaması oluşturur.</span><span class="sxs-lookup"><span data-stu-id="5a76e-130">It produces a sample Todo application that is outwardly identical to the KnockoutJS SPA template.</span></span> <span data-ttu-id="5a76e-131">İç, AJAX veri katmanı ile kolay yerini alır, iki karşılaştırmak için yan yana yaklaşıyor.</span><span class="sxs-lookup"><span data-stu-id="5a76e-131">On the inside, it replaces the AJAX data layer with Breeze, so you can compare the two approaches side-by-side.</span></span> <span data-ttu-id="5a76e-132">Elbette, bir kolay uygulama olasılığı neredeyse hiç dokunur.</span><span class="sxs-lookup"><span data-stu-id="5a76e-132">Of course, it barely touches the potential of a Breeze application.</span></span> <span data-ttu-id="5a76e-133">Ancak, kolay nasıl çalıştığını görürsünüz ve nasıl biraz geçiş yapmak için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="5a76e-133">But you'll see how Breeze works and how little is required to make that transition.</span></span>

<span data-ttu-id="5a76e-134">Haydi başlayalım.</span><span class="sxs-lookup"><span data-stu-id="5a76e-134">Let's get started.</span></span>

## <a name="create-a-breezeknockout-template-project"></a><span data-ttu-id="5a76e-135">Bir kolay/Boşaltılan şablonu projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="5a76e-135">Create a Breeze/Knockout Template Project</span></span>

<span data-ttu-id="5a76e-136">İndirin ve şablonu yukarıdaki karşıdan yükleme düğmesini tıklatarak yükleyin.</span><span class="sxs-lookup"><span data-stu-id="5a76e-136">Download and install the template by clicking the Download button above.</span></span> <span data-ttu-id="5a76e-137">Şablonu bir Visual Studio Uzantısı (VSIX) dosyası olarak paketlenir.</span><span class="sxs-lookup"><span data-stu-id="5a76e-137">The template is packaged as a Visual Studio Extension (VSIX) file.</span></span> <span data-ttu-id="5a76e-138">Visual Studio yeniden başlatmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="5a76e-138">You might need to restart Visual Studio.</span></span>

<span data-ttu-id="5a76e-139">İçinde **şablonları** bölmesinde, **yüklü şablonlar** ve genişletin **Visual C#** düğümü.</span><span class="sxs-lookup"><span data-stu-id="5a76e-139">In the **Templates** pane, select **Installed Templates** and expand the **Visual C#** node.</span></span> <span data-ttu-id="5a76e-140">Altında **Visual C#**seçin **Web**.</span><span class="sxs-lookup"><span data-stu-id="5a76e-140">Under **Visual C#**, select **Web**.</span></span> <span data-ttu-id="5a76e-141">Proje şablonları listesinde seçin **ASP.NET MVC 4 Web uygulaması**.</span><span class="sxs-lookup"><span data-stu-id="5a76e-141">In the list of project templates, select **ASP.NET MVC 4 Web Application**.</span></span> <span data-ttu-id="5a76e-142">Proje adı ve'ı tıklatın **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="5a76e-142">Name the project and click **OK**.</span></span>

<span data-ttu-id="5a76e-143">İçinde **yeni proje** seçin **kolay Boşaltılan SPA**.</span><span class="sxs-lookup"><span data-stu-id="5a76e-143">In the **New Project** wizard, select **Breeze Knockout SPA**.</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/SelectBreezeKOSpaTemplate.png)

<span data-ttu-id="5a76e-144">Derleme ve hata ayıklama olmadan uygulamayı çalıştırmak için CTRL-F5 tuşuna basın veya hata ayıklama ile çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="5a76e-144">Press Ctrl-F5 to build and run the application without debugging, or press F5 to run with debugging.</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/ZephyrRunning.png)

<span data-ttu-id="5a76e-145">Uygulamayı ilk kez çalıştırdığında, oturum açma ekranı görüntüler.</span><span class="sxs-lookup"><span data-stu-id="5a76e-145">When the application first runs, it displays a login screen.</span></span> <span data-ttu-id="5a76e-146">"Kaydolma" bağlantısına tıklayın ve bir kullanıcı adı ve parola girebileceğiniz yeni bir sayfa görünümü içine glides.</span><span class="sxs-lookup"><span data-stu-id="5a76e-146">Click the "Sign up" link and a new page glides into view, where you can enter a username and password.</span></span> <span data-ttu-id="5a76e-147">(Oturum açma ve kayıt sayfaları ASP.NET MVC kullanılarak oluşturulur.) Kayıt formu gönderdiğinde, sunucu, hesabınız için iki öğeli bir Yapılacaklar listesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="5a76e-147">(The login and registration pages are built using ASP.NET MVC.) When you submit the registration form, the server generates a TodoList with two items for your account.</span></span> <span data-ttu-id="5a76e-148">Ardından, bunları size sarı bir not üzerinde gösterir.</span><span class="sxs-lookup"><span data-stu-id="5a76e-148">Then it presents them to you on a yellow note.</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/TodoList.png)

<span data-ttu-id="5a76e-149">Artık, kara SPA bulunur.</span><span class="sxs-lookup"><span data-stu-id="5a76e-149">Now you are in the land of SPA.</span></span> <span data-ttu-id="5a76e-150">Her şeyi, görebilir ve Todos düzenleme işlenmiş ve Knockout ve kolay Yardım ile istemcide yönetilen karşılaşırsınız.</span><span class="sxs-lookup"><span data-stu-id="5a76e-150">Everything you see and experience while manipulating Todos is rendered and managed on the client with the help of Knockout and Breeze.</span></span> <span data-ttu-id="5a76e-151">Uygulama bir kullanıcı olarak keşfedin...</span><span class="sxs-lookup"><span data-stu-id="5a76e-151">Explore the app as a user …</span></span> <span data-ttu-id="5a76e-152">Ancak bir geliştiricinin göz.</span><span class="sxs-lookup"><span data-stu-id="5a76e-152">but with a developer's eye.</span></span> <span data-ttu-id="5a76e-153">Ağ trafiğini yakalamak için tarayıcınızda geliştirici araçlarını kullanın.</span><span class="sxs-lookup"><span data-stu-id="5a76e-153">Use the developer tools in your browser to capture the network traffic.</span></span> <span data-ttu-id="5a76e-154">(Internet Explorer'da: F12 tuşuna basın, select **ağ** sekmesine ve tıklayın **Yakalamayı Başlat**.) Şimdi aşağıdakileri deneyin:</span><span class="sxs-lookup"><span data-stu-id="5a76e-154">(In Internet Explorer: Press F12, select the **Network** tab, and click **Start capturing**.) Now try the following:</span></span>

- <span data-ttu-id="5a76e-155">Yeni bir Yapılacaklar öğesi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="5a76e-155">Add a new Todo item.</span></span>
- <span data-ttu-id="5a76e-156">Etiket'i tıklatın ve Yapılacaklar öğesi başlık Düzenle</span><span class="sxs-lookup"><span data-stu-id="5a76e-156">Click the label and edit the Todo item title</span></span>
- <span data-ttu-id="5a76e-157">Öğesi Bitti'yi işaretlemek için onay kutusunu işaretleyin.</span><span class="sxs-lookup"><span data-stu-id="5a76e-157">Check a checkbox to mark the item done.</span></span> <span data-ttu-id="5a76e-158">Başlık artık düzenlenemez şekilde textbox devre dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="5a76e-158">Notice that the textbox is disabled, so the title is no longer editable.</span></span>
- <span data-ttu-id="5a76e-159">Etiket sağındaki 'x' tıklayın.</span><span class="sxs-lookup"><span data-stu-id="5a76e-159">Click the ‘x' to the right of the label.</span></span> <span data-ttu-id="5a76e-160">Öğe kaybolur ve veritabanından silinir.</span><span class="sxs-lookup"><span data-stu-id="5a76e-160">The item disappears and is deleted from the database.</span></span>
- <span data-ttu-id="5a76e-161">Başka bir öğe seçin ve başlığını temizleyin.</span><span class="sxs-lookup"><span data-stu-id="5a76e-161">Pick another item and clear its title.</span></span> <span data-ttu-id="5a76e-162">Başlık gerekli bir doğrulama hata iletisi alırsınız.</span><span class="sxs-lookup"><span data-stu-id="5a76e-162">You'll get a validation error that the title is required.</span></span> <span data-ttu-id="5a76e-163">Kısa bir duraklamadan sonra önceki başlık geri yüklendi.</span><span class="sxs-lookup"><span data-stu-id="5a76e-163">After a brief pause, the previous title is restored.</span></span>
- <span data-ttu-id="5a76e-164">Gerçekten uzun bir başlık yazın.</span><span class="sxs-lookup"><span data-stu-id="5a76e-164">Type in a ridiculously long title.</span></span> <span data-ttu-id="5a76e-165">Başlık çok uzun olduğundan farklı doğrulama hatası alırsınız.</span><span class="sxs-lookup"><span data-stu-id="5a76e-165">You'll get a different validation error that the title is too long.</span></span>
- <span data-ttu-id="5a76e-166">"Yapılacaklar listesine ekle" düğmesini tıklatın.</span><span class="sxs-lookup"><span data-stu-id="5a76e-166">Click the "Add Todo List" button.</span></span> <span data-ttu-id="5a76e-167">Yeni bir liste önceki listede solunda görünür.</span><span class="sxs-lookup"><span data-stu-id="5a76e-167">A new list appears to the left of the previous list.</span></span>
- <span data-ttu-id="5a76e-168">TodoList başlık, gerekliyse tetikleme ve uzunluğu doğrulamaları yürütün.</span><span class="sxs-lookup"><span data-stu-id="5a76e-168">Play with the TodoList title, triggering its required and length validations.</span></span>
- <span data-ttu-id="5a76e-169">Hata iletisi temizlemek için başlık metin kutusuna tıklayın.</span><span class="sxs-lookup"><span data-stu-id="5a76e-169">Click in the title textbox to clear the error message.</span></span>
- <span data-ttu-id="5a76e-170">Daire içinde TodoList ve kendi todos silmek için sağ üst köşesindeki "x"'i tıklatın.</span><span class="sxs-lookup"><span data-stu-id="5a76e-170">Click the "x" in the circle in the upper right corner to delete the TodoList and its todos.</span></span>

<span data-ttu-id="5a76e-171">Doğrulama mantığını kolay tarafından gerçekleştirilen istemci-tarafı ' dir.</span><span class="sxs-lookup"><span data-stu-id="5a76e-171">The validation logic is performed client-side by Breeze.</span></span> <span data-ttu-id="5a76e-172">Sunucu modeli sınıfları doğrulama öznitelikleri istemciye yayılan ve istemci sunucusuyla bağlantı kurar önce otomatik olarak yürütülür.</span><span class="sxs-lookup"><span data-stu-id="5a76e-172">Validation attributes on the server model classes are propagated to the client and executed automatically before the client contacts the server.</span></span>

<span data-ttu-id="5a76e-173">Ağ trafiği gözden geçirin.</span><span class="sxs-lookup"><span data-stu-id="5a76e-173">Review the network traffic.</span></span> <span data-ttu-id="5a76e-174">Kolay bir hata algılandığında sunucuya hiçbir çağrılar olduğunu dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="5a76e-174">Notice that there were no calls to the server when Breeze detected an error.</span></span> <span data-ttu-id="5a76e-175">Her geçerli değişikliği bir POST isteğinin sonuçlandı "/ Todo/api/SaveChanges".</span><span class="sxs-lookup"><span data-stu-id="5a76e-175">Each valid change resulted in a POST request to "/api/Todo/SaveChanges".</span></span> <span data-ttu-id="5a76e-176">Kolay değişiklikleri sunmaktadır ve Web API denetleyicinin birlikte tek bir istek gönderir `SaveChanges` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="5a76e-176">Breeze bundles the changes and sends them together as a single request to the Web API controller's `SaveChanges` method.</span></span> <span data-ttu-id="5a76e-177">PUT, POST ve silme istekleri her öğe için ayrı ayrı yapar KockoutJS SPA şablonundan farklı olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="5a76e-177">That's different from KockoutJS SPA template, which makes PUT, POST, and DELETE requests for each item individually.</span></span>

## <a name="peek-inside"></a><span data-ttu-id="5a76e-178">İçinde Gözat</span><span class="sxs-lookup"><span data-stu-id="5a76e-178">Peek inside</span></span>

<span data-ttu-id="5a76e-179">Bu uygulama, istemci tarafı ve sunucu tarafındaki vardır.</span><span class="sxs-lookup"><span data-stu-id="5a76e-179">This application has a client side and a server side.</span></span> <span data-ttu-id="5a76e-180">Üçüncü taraf JavaScript kitaplıklarını ("Betikleri" klasöründe) artı küçük bir HTML ve uygulama JavaScript modülleri ("uygulama" klasöründe) birleşimini, istemci-tarafı yığını oluşur.</span><span class="sxs-lookup"><span data-stu-id="5a76e-180">The client-side stack consists of a little HTML and a combination of application JavaScript modules (in the "app" folder) plus third-party JavaScript libraries (in the "Scripts" folder).</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/ClientArchitecture.png)

<span data-ttu-id="5a76e-181">Çakıştırmaları SPA şablon araştırılan varsa, bu tanıdık gelecektir.</span><span class="sxs-lookup"><span data-stu-id="5a76e-181">If you've investigated the KnockoutJS SPA template, this should look very familiar.</span></span> <span data-ttu-id="5a76e-182">Mavi kutuları odaklanın.</span><span class="sxs-lookup"><span data-stu-id="5a76e-182">Focus on the blue boxes.</span></span> <span data-ttu-id="5a76e-183">Model-View-ViewModel (hangi görünümün HTML pencere öğeleri düzgün bir şekilde görünüm modeli destekleyen sunu koddan ayrılmış MVVM), kullanıcı Arabirimi mimarisidir.</span><span class="sxs-lookup"><span data-stu-id="5a76e-183">The UI architecture is Model-View-ViewModel (MVVM), in which the HTML widgets of the view are cleanly separated from the supporting presentation code in the view-model.</span></span> <span data-ttu-id="5a76e-184">Her, diğer intimate bilgisi olmadan işini yapabilmesi için bir veri bağlama sistemine (Bu durumda Boşaltılan) görünümü ve görünüm modeli düzenler.</span><span class="sxs-lookup"><span data-stu-id="5a76e-184">A data binding system (Knockout in this case) coordinates the view and view-model so that each can do its job without intimate knowledge of the other.</span></span>

<span data-ttu-id="5a76e-185">Model Yapılacaklar verileri saklar.</span><span class="sxs-lookup"><span data-stu-id="5a76e-185">The model encapsulates the Todo data.</span></span> <span data-ttu-id="5a76e-186">Görünümünde pencere öğeleri için doğrudan bağlanabilir şekilde modeldeki varlıklar Boşaltılan observable özelliklerle kolay tarafından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="5a76e-186">Entities in the model are constructed by Breeze with Knockout observable properties, so they can be bound directly to widgets in the view.</span></span> <span data-ttu-id="5a76e-187">Görünüm modeli edinmeli ve model varlıklar kaydetmek için veri bağlamı sorar.</span><span class="sxs-lookup"><span data-stu-id="5a76e-187">The view-model asks the data context to acquire and save the model entities.</span></span> <span data-ttu-id="5a76e-188">Veri bağlamı kolay işin çoğunu atar.</span><span class="sxs-lookup"><span data-stu-id="5a76e-188">The data context delegates most of the work to Breeze.</span></span>

<span data-ttu-id="5a76e-189">Sunucu tarafı yığını bazı geliştirici kodu ve üç ilkesi .NET kitaplıklarına oluşur: Web API, Entity Framework ve Breeze.NET:</span><span class="sxs-lookup"><span data-stu-id="5a76e-189">The server-side stack consists of some developer code and three principle .NET libraries: Web API, Entity Framework, and Breeze.NET:</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/ServerArchitecture.png)

<span data-ttu-id="5a76e-190">Temel mimari KockoutJS SPA şablonu ile aynıdır.</span><span class="sxs-lookup"><span data-stu-id="5a76e-190">The basic architecture is the same as the KockoutJS SPA template.</span></span> <span data-ttu-id="5a76e-191">Ancak, uygulama çok daha kolaydır: DTOs silindi ve Entity Framework ayrıntıları çoğunu Breeze.NET için temsilci seçilmiş.</span><span class="sxs-lookup"><span data-stu-id="5a76e-191">However, the implementation is much simpler: The DTOs were deleted, and most of the Entity Framework details have been delegated to Breeze.NET.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5a76e-192">Sonraki Adımlar</span><span class="sxs-lookup"><span data-stu-id="5a76e-192">Next Steps</span></span>

<span data-ttu-id="5a76e-193">Tarafından destekli kodu, keşfetme önerdiğimiz [kapsamlı tartışma](http://www.breezejs.com/spa-template?utm_source=ms-spa) hem istemci hem de sunucu yığınları kolay Web sitesi.</span><span class="sxs-lookup"><span data-stu-id="5a76e-193">We suggest that you explore the code, guided by the [extensive discussion](http://www.breezejs.com/spa-template?utm_source=ms-spa) of both the client and the server stacks on the Breeze website.</span></span>

<span data-ttu-id="5a76e-194">Kolay istemci-tarafı sorgusu yürütmeyi deneyin; Bazı filtreler ve sıralar ekleyin.</span><span class="sxs-lookup"><span data-stu-id="5a76e-194">You might try playing with Breeze client-side query; add some filters and sorts.</span></span> <span data-ttu-id="5a76e-195">Daha fazla model özellikleri ve uçtan uca SPA geliştirme için daha iyi bir fikir almak için daha fazla varlık ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5a76e-195">You might add more model properties and more entities to get a better feel for end-to-end SPA development.</span></span> <span data-ttu-id="5a76e-196">Tasarımını olduğunuzda Yapılacaklar özellikleri kesmeden ve bunları kendi ile değiştirin.</span><span class="sxs-lookup"><span data-stu-id="5a76e-196">When you are confident of the design, you can tear out the Todo features and replace them with your own.</span></span>

<span data-ttu-id="5a76e-197">Hemen bir sonraki büyük adım için hazır olacak: istemci-tarafı ekranlar ekleme ve bunlar arasında gezinme.</span><span class="sxs-lookup"><span data-stu-id="5a76e-197">Soon you'll be ready for the next big step: Adding client-side screens and navigating among them.</span></span> <span data-ttu-id="5a76e-198">Bu SPA şablon ardınızda ve bir daha kapsamlı SPA yığınına gibi açın [John Papa'nın etkin havlu](https://github.com/johnpapa/HotTowel#readme "etkin havlu"), kolay ve çakıştırma Karışıma Durandal ekler.</span><span class="sxs-lookup"><span data-stu-id="5a76e-198">You'll leave this SPA template behind and turn to a more complete SPA stack, such as [John Papa's Hot Towel](https://github.com/johnpapa/HotTowel#readme "Hot Towel"), which adds Durandal to the Breeze and Knockout mix.</span></span>