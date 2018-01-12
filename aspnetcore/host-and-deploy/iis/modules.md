---
title: "ASP.NET Core ile IIS modüllerini kullanma"
author: guardrex
description: "ASP.NET Core uygulamaları için etkin ve etkin olmayan IIS modüllerini açıklayan başvuru belgesi."
ms.author: riande
manager: wpickett
ms.custom: mvc
ms.date: 03/08/2017
ms.topic: article
ms.technology: aspnet
ms.prod: aspnet-core
uid: host-and-deploy/iis/modules
ms.openlocfilehash: b52327523467600ff62289022434a77af5d8fa22
ms.sourcegitcommit: 12e5194936b7e820efc5505a2d5d4f84e88eb5ef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2018
---
# <a name="using-iis-modules-with-aspnet-core"></a><span data-ttu-id="61184-103">ASP.NET çekirdeği ile IIS modüllerini kullanma</span><span class="sxs-lookup"><span data-stu-id="61184-103">Using IIS Modules with ASP.NET Core</span></span>

<span data-ttu-id="61184-104">Tarafından [Luke Latham](https://github.com/guardrex)</span><span class="sxs-lookup"><span data-stu-id="61184-104">By [Luke Latham](https://github.com/guardrex)</span></span>

<span data-ttu-id="61184-105">ASP.NET Core uygulamaları IIS tarafından bir ters proxy yapılandırması barındırılır.</span><span class="sxs-lookup"><span data-stu-id="61184-105">ASP.NET Core applications are hosted by IIS in a reverse proxy configuration.</span></span> <span data-ttu-id="61184-106">Bazı yerel IIS modülleri ve tüm yönetilen IIS modülleri ASP.NET Core uygulamaları için istekleri işlemek kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="61184-106">Some of the native IIS modules and all of the IIS managed modules aren't available to process requests for ASP.NET Core apps.</span></span> <span data-ttu-id="61184-107">Çoğu durumda, ASP.NET Core IIS yerel ve yönetilen modülleri özelliklerine bir alternatif sunar.</span><span class="sxs-lookup"><span data-stu-id="61184-107">In many cases, ASP.NET Core offers an alternative to the features of IIS native and managed modules.</span></span>

## <a name="native-modules"></a><span data-ttu-id="61184-108">Yerel modülleri</span><span class="sxs-lookup"><span data-stu-id="61184-108">Native Modules</span></span>

<span data-ttu-id="61184-109">Modül</span><span class="sxs-lookup"><span data-stu-id="61184-109">Module</span></span> | <span data-ttu-id="61184-110">.NET core etkin</span><span class="sxs-lookup"><span data-stu-id="61184-110">.NET Core Active</span></span> | <span data-ttu-id="61184-111">ASP.NET çekirdeği seçeneği</span><span class="sxs-lookup"><span data-stu-id="61184-111">ASP.NET Core Option</span></span>
--- | :---: | ---
<span data-ttu-id="61184-112">**Anonim kimlik doğrulaması**</span><span class="sxs-lookup"><span data-stu-id="61184-112">**Anonymous Authentication**</span></span><br>`AnonymousAuthenticationModule` | <span data-ttu-id="61184-113">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-113">Yes</span></span> | 
<span data-ttu-id="61184-114">**Temel Kimlik Doğrulaması**</span><span class="sxs-lookup"><span data-stu-id="61184-114">**Basic Authentication**</span></span><br>`BasicAuthenticationModule` | <span data-ttu-id="61184-115">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-115">Yes</span></span> | 
<span data-ttu-id="61184-116">**İstemci sertifika eşlemesi kimlik doğrulaması**</span><span class="sxs-lookup"><span data-stu-id="61184-116">**Client Certification Mapping Authentication**</span></span><br>`CertificateMappingAuthenticationModule` | <span data-ttu-id="61184-117">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-117">Yes</span></span> | 
<span data-ttu-id="61184-118">**CGI**</span><span class="sxs-lookup"><span data-stu-id="61184-118">**CGI**</span></span><br>`CgiModule` | <span data-ttu-id="61184-119">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-119">No</span></span> | 
<span data-ttu-id="61184-120">**Yapılandırma Doğrulama**</span><span class="sxs-lookup"><span data-stu-id="61184-120">**Configuration Validation**</span></span><br>`ConfigurationValidationModule` | <span data-ttu-id="61184-121">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-121">Yes</span></span> | 
<span data-ttu-id="61184-122">**HTTP Hataları**</span><span class="sxs-lookup"><span data-stu-id="61184-122">**HTTP Errors**</span></span><br>`CustomErrorModule` | <span data-ttu-id="61184-123">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-123">No</span></span> | [<span data-ttu-id="61184-124">Durum kodu sayfaları Ara</span><span class="sxs-lookup"><span data-stu-id="61184-124">Status Code Pages Middleware</span></span>](xref:fundamentals/error-handling#configuring-status-code-pages)
<span data-ttu-id="61184-125">**Özel günlüğe kaydetme**</span><span class="sxs-lookup"><span data-stu-id="61184-125">**Custom Logging**</span></span><br>`CustomLoggingModule` | <span data-ttu-id="61184-126">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-126">Yes</span></span> | 
<span data-ttu-id="61184-127">**Varsayılan Belge**</span><span class="sxs-lookup"><span data-stu-id="61184-127">**Default Document**</span></span><br>`DefaultDocumentModule` | <span data-ttu-id="61184-128">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-128">No</span></span> | [<span data-ttu-id="61184-129">Varsayılan dosya ara yazılımı</span><span class="sxs-lookup"><span data-stu-id="61184-129">Default Files Middleware</span></span>](xref:fundamentals/static-files#serving-a-default-document)
<span data-ttu-id="61184-130">**Özet kimlik doğrulaması**</span><span class="sxs-lookup"><span data-stu-id="61184-130">**Digest Authentication**</span></span><br>`DigestAuthenticationModule` | <span data-ttu-id="61184-131">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-131">Yes</span></span> | 
<span data-ttu-id="61184-132">**Dizin Tarama**</span><span class="sxs-lookup"><span data-stu-id="61184-132">**Directory Browsing**</span></span><br>`DirectoryListingModule` | <span data-ttu-id="61184-133">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-133">No</span></span> | [<span data-ttu-id="61184-134">Dizin tarama Ara</span><span class="sxs-lookup"><span data-stu-id="61184-134">Directory Browsing Middleware</span></span>](xref:fundamentals/static-files#enabling-directory-browsing)
<span data-ttu-id="61184-135">**Dinamik sıkıştırma**</span><span class="sxs-lookup"><span data-stu-id="61184-135">**Dynamic Compression**</span></span><br>`DynamicCompressionModule` | <span data-ttu-id="61184-136">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-136">Yes</span></span> | [<span data-ttu-id="61184-137">Yanıt Sıkıştırma Ara Yazılımı</span><span class="sxs-lookup"><span data-stu-id="61184-137">Response Compression Middleware</span></span>](xref:performance/response-compression)
<span data-ttu-id="61184-138">**İzleme**</span><span class="sxs-lookup"><span data-stu-id="61184-138">**Tracing**</span></span><br>`FailedRequestsTracingModule` | <span data-ttu-id="61184-139">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-139">Yes</span></span> | [<span data-ttu-id="61184-140">ASP.NET çekirdeği günlüğü</span><span class="sxs-lookup"><span data-stu-id="61184-140">ASP.NET Core Logging</span></span>](xref:fundamentals/logging/index#the-tracesource-provider)
<span data-ttu-id="61184-141">**Dosyayı önbelleğe alma**</span><span class="sxs-lookup"><span data-stu-id="61184-141">**File Caching**</span></span><br>`FileCacheModule` | <span data-ttu-id="61184-142">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-142">No</span></span> | [<span data-ttu-id="61184-143">Yanıtları Önbelleğe Alma Ara Yazılımı</span><span class="sxs-lookup"><span data-stu-id="61184-143">Response Caching Middleware</span></span>](xref:performance/caching/middleware)
<span data-ttu-id="61184-144">**HTTP önbelleğe alma**</span><span class="sxs-lookup"><span data-stu-id="61184-144">**HTTP Caching**</span></span><br>`HttpCacheModule` | <span data-ttu-id="61184-145">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-145">No</span></span> | [<span data-ttu-id="61184-146">Yanıtları Önbelleğe Alma Ara Yazılımı</span><span class="sxs-lookup"><span data-stu-id="61184-146">Response Caching Middleware</span></span>](xref:performance/caching/middleware)
<span data-ttu-id="61184-147">**HTTP Günlüğü**</span><span class="sxs-lookup"><span data-stu-id="61184-147">**HTTP Logging**</span></span><br>`HttpLoggingModule` | <span data-ttu-id="61184-148">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-148">Yes</span></span> | [<span data-ttu-id="61184-149">ASP.NET çekirdeği günlüğü</span><span class="sxs-lookup"><span data-stu-id="61184-149">ASP.NET Core Logging</span></span>](xref:fundamentals/logging/index)<br><span data-ttu-id="61184-150">Uygulamaları: [elmah.io](https://github.com/elmahio/Elmah.Io.Extensions.Logging), [Loggr](https://github.com/imobile3/Loggr.Extensions.Logging), [NLog](https://github.com/NLog/NLog.Extensions.Logging), [Serilog](https://github.com/serilog/serilog-extensions-logging)</span><span class="sxs-lookup"><span data-stu-id="61184-150">Implementations: [elmah.io](https://github.com/elmahio/Elmah.Io.Extensions.Logging), [Loggr](https://github.com/imobile3/Loggr.Extensions.Logging), [NLog](https://github.com/NLog/NLog.Extensions.Logging), [Serilog](https://github.com/serilog/serilog-extensions-logging)</span></span>
<span data-ttu-id="61184-151">**HTTP Yeniden Yönlendirmesi**</span><span class="sxs-lookup"><span data-stu-id="61184-151">**HTTP Redirection**</span></span><br>`HttpRedirectionModule` | <span data-ttu-id="61184-152">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-152">Yes</span></span> | [<span data-ttu-id="61184-153">URL Yeniden Yazma Ara Yazılımı</span><span class="sxs-lookup"><span data-stu-id="61184-153">URL Rewriting Middleware</span></span>](xref:fundamentals/url-rewriting)
<span data-ttu-id="61184-154">**IIS istemci sertifika eşlemesi kimlik doğrulaması**</span><span class="sxs-lookup"><span data-stu-id="61184-154">**IIS Client Certificate Mapping Authentication**</span></span><br>`IISCertificateMappingAuthenticationModule` | <span data-ttu-id="61184-155">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-155">Yes</span></span> | 
<span data-ttu-id="61184-156">**IP ve Etki Alanı Kısıtlamaları**</span><span class="sxs-lookup"><span data-stu-id="61184-156">**IP and Domain Restrictions**</span></span><br>`IpRestrictionModule` | <span data-ttu-id="61184-157">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-157">Yes</span></span> | 
<span data-ttu-id="61184-158">**ISAPI Filtreleri**</span><span class="sxs-lookup"><span data-stu-id="61184-158">**ISAPI Filters**</span></span><br>`IsapiFilterModule` | <span data-ttu-id="61184-159">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-159">Yes</span></span> | [<span data-ttu-id="61184-160">Ara Yazılım</span><span class="sxs-lookup"><span data-stu-id="61184-160">Middleware</span></span>](xref:fundamentals/middleware)
<span data-ttu-id="61184-161">**ISAPI**</span><span class="sxs-lookup"><span data-stu-id="61184-161">**ISAPI**</span></span><br>`IsapiModule` | <span data-ttu-id="61184-162">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-162">Yes</span></span> | [<span data-ttu-id="61184-163">Ara Yazılım</span><span class="sxs-lookup"><span data-stu-id="61184-163">Middleware</span></span>](xref:fundamentals/middleware)
<span data-ttu-id="61184-164">**Protokol desteği**</span><span class="sxs-lookup"><span data-stu-id="61184-164">**Protocol Support**</span></span><br>`ProtocolSupportModule` | <span data-ttu-id="61184-165">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-165">Yes</span></span> | 
<span data-ttu-id="61184-166">**İstek Filtreleme**</span><span class="sxs-lookup"><span data-stu-id="61184-166">**Request Filtering**</span></span><br>`RequestFilteringModule` | <span data-ttu-id="61184-167">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-167">Yes</span></span> | [<span data-ttu-id="61184-168">URL yeniden yazma işlemi Ara`IRule`</span><span class="sxs-lookup"><span data-stu-id="61184-168">URL Rewriting Middleware `IRule`</span></span>](xref:fundamentals/url-rewriting#irule-based-rule)
<span data-ttu-id="61184-169">**İstek İzleyicisi**</span><span class="sxs-lookup"><span data-stu-id="61184-169">**Request Monitor**</span></span><br>`RequestMonitorModule` | <span data-ttu-id="61184-170">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-170">Yes</span></span> | 
<span data-ttu-id="61184-171">**URL yeniden yazma işlemi**</span><span class="sxs-lookup"><span data-stu-id="61184-171">**URL Rewriting**</span></span><br>`RewriteModule` | <span data-ttu-id="61184-172">Yes†</span><span class="sxs-lookup"><span data-stu-id="61184-172">Yes†</span></span> | [<span data-ttu-id="61184-173">URL Yeniden Yazma Ara Yazılımı</span><span class="sxs-lookup"><span data-stu-id="61184-173">URL Rewriting Middleware</span></span>](xref:fundamentals/url-rewriting)
<span data-ttu-id="61184-174">**Sunucu Tarafına Şunlar Dahildir**</span><span class="sxs-lookup"><span data-stu-id="61184-174">**Server Side Includes**</span></span><br>`ServerSideIncludeModule` | <span data-ttu-id="61184-175">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-175">No</span></span> | 
<span data-ttu-id="61184-176">**Statik sıkıştırma**</span><span class="sxs-lookup"><span data-stu-id="61184-176">**Static Compression**</span></span><br>`StaticCompressionModule` | <span data-ttu-id="61184-177">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-177">No</span></span> | [<span data-ttu-id="61184-178">Yanıt Sıkıştırma Ara Yazılımı</span><span class="sxs-lookup"><span data-stu-id="61184-178">Response Compression Middleware</span></span>](xref:performance/response-compression)
<span data-ttu-id="61184-179">**Statik İçerik**</span><span class="sxs-lookup"><span data-stu-id="61184-179">**Static Content**</span></span><br>`StaticFileModule` | <span data-ttu-id="61184-180">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-180">No</span></span> | [<span data-ttu-id="61184-181">Statik dosya ara yazılımı</span><span class="sxs-lookup"><span data-stu-id="61184-181">Static File Middleware</span></span>](xref:fundamentals/static-files)
<span data-ttu-id="61184-182">**Belirteç önbelleğe alma**</span><span class="sxs-lookup"><span data-stu-id="61184-182">**Token Caching**</span></span><br>`TokenCacheModule` | <span data-ttu-id="61184-183">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-183">Yes</span></span> | 
<span data-ttu-id="61184-184">**URI önbelleği**</span><span class="sxs-lookup"><span data-stu-id="61184-184">**URI Caching**</span></span><br>`UriCacheModule` | <span data-ttu-id="61184-185">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-185">Yes</span></span> | 
<span data-ttu-id="61184-186">**URL Yetkilendirmesi**</span><span class="sxs-lookup"><span data-stu-id="61184-186">**URL Authorization**</span></span><br>`UrlAuthorizationModule` | <span data-ttu-id="61184-187">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-187">Yes</span></span> | [<span data-ttu-id="61184-188">ASP.NET Core kimliği</span><span class="sxs-lookup"><span data-stu-id="61184-188">ASP.NET Core Identity</span></span>](xref:security/authentication/identity)
<span data-ttu-id="61184-189">**Windows kimlik doğrulaması**</span><span class="sxs-lookup"><span data-stu-id="61184-189">**Windows Authentication**</span></span><br>`WindowsAuthenticationModule` | <span data-ttu-id="61184-190">Evet</span><span class="sxs-lookup"><span data-stu-id="61184-190">Yes</span></span> | 

<span data-ttu-id="61184-191">†The URL yeniden yazma modülü 's `isFile` ve `isDirectory` değişiklikleri nedeniyle ASP.NET Core uygulamaları ile çalışmıyor [dizin yapısını](xref:host-and-deploy/directory-structure).</span><span class="sxs-lookup"><span data-stu-id="61184-191">†The URL Rewrite Module's `isFile` and `isDirectory` don't work with ASP.NET Core apps due to the changes in [directory structure](xref:host-and-deploy/directory-structure).</span></span>

## <a name="managed-modules"></a><span data-ttu-id="61184-192">Yönetilen modüller</span><span class="sxs-lookup"><span data-stu-id="61184-192">Managed Modules</span></span>

<span data-ttu-id="61184-193">Modül</span><span class="sxs-lookup"><span data-stu-id="61184-193">Module</span></span> | <span data-ttu-id="61184-194">.NET core etkin</span><span class="sxs-lookup"><span data-stu-id="61184-194">.NET Core Active</span></span> | <span data-ttu-id="61184-195">ASP.NET çekirdeği seçeneği</span><span class="sxs-lookup"><span data-stu-id="61184-195">ASP.NET Core Option</span></span>
--- | :---: | ---
<span data-ttu-id="61184-196">AnonymousIdentification</span><span class="sxs-lookup"><span data-stu-id="61184-196">AnonymousIdentification</span></span> | <span data-ttu-id="61184-197">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-197">No</span></span> | 
<span data-ttu-id="61184-198">DefaultAuthentication</span><span class="sxs-lookup"><span data-stu-id="61184-198">DefaultAuthentication</span></span> | <span data-ttu-id="61184-199">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-199">No</span></span> | 
<span data-ttu-id="61184-200">FileAuthorization</span><span class="sxs-lookup"><span data-stu-id="61184-200">FileAuthorization</span></span> | <span data-ttu-id="61184-201">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-201">No</span></span> | 
<span data-ttu-id="61184-202">FormsAuthentication</span><span class="sxs-lookup"><span data-stu-id="61184-202">FormsAuthentication</span></span> | <span data-ttu-id="61184-203">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-203">No</span></span> | [<span data-ttu-id="61184-204">Tanımlama bilgisi kimlik doğrulaması ara yazılımı</span><span class="sxs-lookup"><span data-stu-id="61184-204">Cookie Authentication Middleware</span></span>](xref:security/authentication/cookie)
<span data-ttu-id="61184-205">OutputCache</span><span class="sxs-lookup"><span data-stu-id="61184-205">OutputCache</span></span> | <span data-ttu-id="61184-206">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-206">No</span></span> | [<span data-ttu-id="61184-207">Yanıtları Önbelleğe Alma Ara Yazılımı</span><span class="sxs-lookup"><span data-stu-id="61184-207">Response Caching Middleware</span></span>](xref:performance/caching/middleware)
<span data-ttu-id="61184-208">Profil</span><span class="sxs-lookup"><span data-stu-id="61184-208">Profile</span></span> | <span data-ttu-id="61184-209">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-209">No</span></span> | 
<span data-ttu-id="61184-210">RoleManager</span><span class="sxs-lookup"><span data-stu-id="61184-210">RoleManager</span></span> | <span data-ttu-id="61184-211">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-211">No</span></span> | 
<span data-ttu-id="61184-212">ScriptModule 4.0</span><span class="sxs-lookup"><span data-stu-id="61184-212">ScriptModule-4.0</span></span> | <span data-ttu-id="61184-213">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-213">No</span></span> | 
<span data-ttu-id="61184-214">Oturum</span><span class="sxs-lookup"><span data-stu-id="61184-214">Session</span></span> | <span data-ttu-id="61184-215">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-215">No</span></span> | [<span data-ttu-id="61184-216">Oturum Ara</span><span class="sxs-lookup"><span data-stu-id="61184-216">Session Middleware</span></span>](xref:fundamentals/app-state)
<span data-ttu-id="61184-217">UrlAuthorization</span><span class="sxs-lookup"><span data-stu-id="61184-217">UrlAuthorization</span></span> | <span data-ttu-id="61184-218">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-218">No</span></span> | 
<span data-ttu-id="61184-219">UrlMappingsModule</span><span class="sxs-lookup"><span data-stu-id="61184-219">UrlMappingsModule</span></span> | <span data-ttu-id="61184-220">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-220">No</span></span> | [<span data-ttu-id="61184-221">URL Yeniden Yazma Ara Yazılımı</span><span class="sxs-lookup"><span data-stu-id="61184-221">URL Rewriting Middleware</span></span>](xref:fundamentals/url-rewriting)
<span data-ttu-id="61184-222">UrlRoutingModule 4.0</span><span class="sxs-lookup"><span data-stu-id="61184-222">UrlRoutingModule-4.0</span></span> | <span data-ttu-id="61184-223">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-223">No</span></span> | [<span data-ttu-id="61184-224">ASP.NET Core kimliği</span><span class="sxs-lookup"><span data-stu-id="61184-224">ASP.NET Core  Identity</span></span>](xref:security/authentication/identity)
<span data-ttu-id="61184-225">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="61184-225">WindowsAuthentication</span></span> | <span data-ttu-id="61184-226">Hayır</span><span class="sxs-lookup"><span data-stu-id="61184-226">No</span></span> | 

## <a name="iis-manager-application-changes"></a><span data-ttu-id="61184-227">IIS Yöneticisi'ni uygulama değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="61184-227">IIS Manager application changes</span></span>

<span data-ttu-id="61184-228">Ayarları yapılandırmak için IIS Yöneticisi'ni kullanarak *web.config* uygulamanın dosya değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="61184-228">Using IIS Manager to configure settings, the *web.config* file of the app is changed.</span></span> <span data-ttu-id="61184-229">Bir uygulama dağıtımı ve de dahil olmak üzere *web.config*, IIS Yöneticisi ile yapılan değişiklikler üzerine tarafından dağıtılan *web.config* dosya.</span><span class="sxs-lookup"><span data-stu-id="61184-229">If deploying an app and including *web.config*, any changes made with IIS Manger are overwritten by the deployed *web.config* file.</span></span> <span data-ttu-id="61184-230">Sunucunun bir değişiklik yaptıysanız *web.config* dosya, güncelleştirilmiş Kopyala *web.config* hemen yerel proje dosyasına.</span><span class="sxs-lookup"><span data-stu-id="61184-230">If changes are made to the server's *web.config* file, copy the updated *web.config* file to the local project immediately.</span></span>

## <a name="disabling-iis-modules"></a><span data-ttu-id="61184-231">IIS modülleri devre dışı bırakma</span><span class="sxs-lookup"><span data-stu-id="61184-231">Disabling IIS modules</span></span>

<span data-ttu-id="61184-232">Bir IIS modülünü sunucu düzeyinde bir uygulama, bir uygulamanın eklemeyi için devre dışı bırakılmalıdır yapılandırılmışsa *web.config* dosya modül devre dışı bırakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="61184-232">If an IIS module is configured at the server level that must be disabled for an app, an addition to the app's *web.config* file can disable the module.</span></span> <span data-ttu-id="61184-233">Modül bırakın ve (varsa) bir yapılandırma ayarını kullanarak devre dışı bırakın ya da uygulamadan modülünü Kaldır.</span><span class="sxs-lookup"><span data-stu-id="61184-233">Either leave the module in place and deactivate it using a configuration setting (if available) or remove the module from the app.</span></span>

### <a name="module-deactivation"></a><span data-ttu-id="61184-234">Modül devre dışı bırakma</span><span class="sxs-lookup"><span data-stu-id="61184-234">Module deactivation</span></span>

<span data-ttu-id="61184-235">Birçok modül olmasını sağlayan bir yapılandırma ayarı bunları uygulamadan kaldırmadan devre dışı sunar.</span><span class="sxs-lookup"><span data-stu-id="61184-235">Many modules offer a configuration setting that allows them to be disabled them without removing them from the app.</span></span> <span data-ttu-id="61184-236">Bir modül devre dışı bırakmak için basit ve hızlı yolu budur.</span><span class="sxs-lookup"><span data-stu-id="61184-236">This is the simplest and quickest way to deactivate a module.</span></span> <span data-ttu-id="61184-237">Örneğin, IIS URL yeniden yazma modülü devre dışı bırakmak isteyen kullanmak `<httpRedirect>` aşağıda gösterildiği gibi öğesi.</span><span class="sxs-lookup"><span data-stu-id="61184-237">For example if wishing to disable the IIS URL Rewrite Module, use the `<httpRedirect>` element as shown below.</span></span> <span data-ttu-id="61184-238">Yapılandırma ayarları modüllerle devre dışı bırakma hakkında daha fazla bilgi için bağlantıları izleyin *alt öğelerini* bölümünü [IIS `<system.webServer>` ](https://docs.microsoft.com/iis/configuration/system.webServer/).</span><span class="sxs-lookup"><span data-stu-id="61184-238">For more information on disabling modules with configuration settings, follow the links in the *Child Elements* section of [IIS `<system.webServer>`](https://docs.microsoft.com/iis/configuration/system.webServer/).</span></span>

```xml
<configuration>
  <system.webServer>
     <httpRedirect enabled="false" />
  </system.webServer>
</configuration>
```

### <a name="module-removal"></a><span data-ttu-id="61184-239">Modül kaldırma</span><span class="sxs-lookup"><span data-stu-id="61184-239">Module removal</span></span>

<span data-ttu-id="61184-240">Bir ayar modülü kaldırmak için kullanmama varsa *web.config*, modülün kilidini açmak ve kilidini `<modules>` bölümünü *web.config* ilk.</span><span class="sxs-lookup"><span data-stu-id="61184-240">If opting to remove a module with a setting in *web.config*, unlock the module and unlock the `<modules>` section of *web.config* first.</span></span> <span data-ttu-id="61184-241">Adımlar aşağıda özetlenen:</span><span class="sxs-lookup"><span data-stu-id="61184-241">The steps are outlined below:</span></span>

1. <span data-ttu-id="61184-242">Sunucu düzeyinde modülü kilidini açın.</span><span class="sxs-lookup"><span data-stu-id="61184-242">Unlock the module at the server level.</span></span> <span data-ttu-id="61184-243">' I tıklatın IIS sunucusunda IIS Yöneticisi'nde **bağlantıları** kenar.</span><span class="sxs-lookup"><span data-stu-id="61184-243">Click on the IIS server in the IIS Manager **Connections** sidebar.</span></span> <span data-ttu-id="61184-244">Açık **modülleri** içinde **IIS** alanı.</span><span class="sxs-lookup"><span data-stu-id="61184-244">Open the **Modules** in the **IIS** area.</span></span> <span data-ttu-id="61184-245">Modül listesinde tıklayın.</span><span class="sxs-lookup"><span data-stu-id="61184-245">Click on the module in the list.</span></span> <span data-ttu-id="61184-246">İçinde **Eylemler** Kenar çubuğunda sağ tıklatın **Unlock**.</span><span class="sxs-lookup"><span data-stu-id="61184-246">In the **Actions** sidebar on the right, click **Unlock**.</span></span> <span data-ttu-id="61184-247">Kaldırmak için planlı olarak gibi birçok modül kilidini *web.config* daha sonra.</span><span class="sxs-lookup"><span data-stu-id="61184-247">Unlock as many modules as are planned to remove from *web.config* later.</span></span>

2. <span data-ttu-id="61184-248">Uygulama olmadan dağıtmak bir `<modules>` bölümüne *web.config*. Bir uygulama ile dağıtılırsa bir *web.config* içeren `<modules>` bölüm önce Configuration Manager IIS Yöneticisi'nde kilidi olmadan bölüm bölümün kilidini çalışılırken bir özel durum oluşturur.</span><span class="sxs-lookup"><span data-stu-id="61184-248">Deploy the app without a `<modules>` section in *web.config*. If an app is deployed with a *web.config* containing the `<modules>` section without having unlocked the section first in the IIS Manager, the Configuration Manager throws an exception when attempting to unlock the section.</span></span> <span data-ttu-id="61184-249">Bu nedenle, uygulamayı olmadan dağıtmak istediğiniz bir `<modules>` bölümü.</span><span class="sxs-lookup"><span data-stu-id="61184-249">Therefore, deploy the app without a `<modules>` section.</span></span>

3. <span data-ttu-id="61184-250">Kilidini `<modules>` bölümünü *web.config*. İçinde **bağlantıları** kenar, Web sitesi tıklatın **siteleri**.</span><span class="sxs-lookup"><span data-stu-id="61184-250">Unlock the `<modules>` section of *web.config*. In the **Connections** sidebar, click the website in **Sites**.</span></span> <span data-ttu-id="61184-251">İçinde **Yönetim** alanında, açık **yapılandırma Düzenleyicisi**.</span><span class="sxs-lookup"><span data-stu-id="61184-251">In the **Management** area, open the **Configuration Editor**.</span></span> <span data-ttu-id="61184-252">Gezinti denetimlerinin seçmek için kullanın `system.webServer/modules` bölümü.</span><span class="sxs-lookup"><span data-stu-id="61184-252">Use the navigation controls to select the `system.webServer/modules` section.</span></span> <span data-ttu-id="61184-253">İçinde **Eylemler** Kenar çubuğunda sağ tıklatıp **Unlock** bölümü.</span><span class="sxs-lookup"><span data-stu-id="61184-253">In the **Actions** sidebar on the right, click to **Unlock** the section.</span></span>

4. <span data-ttu-id="61184-254">Bu noktada, bir `<modules>` bölüm eklenebilir *web.config* ile dosya bir `<remove>` öğesi uygulamadan modülünü Kaldır.</span><span class="sxs-lookup"><span data-stu-id="61184-254">At this point, a `<modules>` section can be added to the *web.config* file with a `<remove>` element to remove the module from the app.</span></span> <span data-ttu-id="61184-255">Birden çok `<remove>` öğeleri, birden fazla modülü kaldırmak için eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="61184-255">Multiple `<remove>` elements can be added to remove multiple modules.</span></span> <span data-ttu-id="61184-256">Olması durumunda unutmayın *web.config* değişiklik yapıldıysa sunucuda yerel olarak projede hemen olmalarını.</span><span class="sxs-lookup"><span data-stu-id="61184-256">Don't forget that if *web.config* changes are made on the server to make them immediately in the project locally.</span></span> <span data-ttu-id="61184-257">Bu şekilde bir modül kaldırma, sunucudaki diğer uygulamalarla modülü kullanımını etkilemez.</span><span class="sxs-lookup"><span data-stu-id="61184-257">Removing a module this way won't affect the use of the module with other apps on the server.</span></span>

  ```xml
  <configuration> 
    <system.webServer> 
      <modules> 
        <remove name="MODULE_NAME" /> 
      </modules> 
    </system.webServer> 
  </configuration>
  ```

<span data-ttu-id="61184-258">Yüklü varsayılan modüllerle bir IIS yüklemesi için aşağıdakileri kullanın `<module>` varsayılan modülleri kaldırmak için bölümü.</span><span class="sxs-lookup"><span data-stu-id="61184-258">For an IIS installation with the default modules installed, use the following `<module>` section to remove the default modules.</span></span>

```xml
<modules>
  <remove name="CustomErrorModule" />
  <remove name="DefaultDocumentModule" />
  <remove name="DirectoryListingModule" />
  <remove name="HttpCacheModule" />
  <remove name="HttpLoggingModule" />
  <remove name="ProtocolSupportModule" />
  <remove name="RequestFilteringModule" />
  <remove name="StaticCompressionModule" /> 
  <remove name="StaticFileModule" /> 
</modules>
```

<span data-ttu-id="61184-259">Bir IIS modülü ile de kaldırılabilir *Appcmd.exe*.</span><span class="sxs-lookup"><span data-stu-id="61184-259">An IIS module can also be removed with *Appcmd.exe*.</span></span> <span data-ttu-id="61184-260">Sağlamak `MODULE_NAME` ve `APPLICATION_NAME` aşağıda gösterilen komuttaki:</span><span class="sxs-lookup"><span data-stu-id="61184-260">Provide the `MODULE_NAME` and `APPLICATION_NAME` in the command shown below:</span></span>

```console
Appcmd.exe delete module MODULE_NAME /app.name:APPLICATION_NAME
```

<span data-ttu-id="61184-261">Nasıl kaldırılacağı işte `DynamicCompressionModule` varsayılan Web sitesinden:</span><span class="sxs-lookup"><span data-stu-id="61184-261">Here's how to remove the `DynamicCompressionModule` from the Default Web Site:</span></span>

```console
%windir%\system32\inetsrv\appcmd.exe delete module DynamicCompressionModule /app.name:"Default Web Site"
```

## <a name="minimum-module-configuration"></a><span data-ttu-id="61184-262">En az modül yapılandırma</span><span class="sxs-lookup"><span data-stu-id="61184-262">Minimum module configuration</span></span>

<span data-ttu-id="61184-263">Bir ASP.NET Core uygulamayı çalıştırmak için gerekli yalnızca Anonim kimlik doğrulama modülünü ve ASP.NET Core modülü modüllerdir.</span><span class="sxs-lookup"><span data-stu-id="61184-263">The only modules required to run an ASP.NET Core app are the Anonymous Authentication Module and the ASP.NET Core Module.</span></span>

![IIS Yöneticisi'ni açmak için modüller gösterilen en az modül yapılandırmasıyla](modules/_static/modules.png)

## <a name="additional-resources"></a><span data-ttu-id="61184-265">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="61184-265">Additional resources</span></span>

* [<span data-ttu-id="61184-266">IIS ile Windows’da barındırma</span><span class="sxs-lookup"><span data-stu-id="61184-266">Host on Windows with IIS</span></span>](xref:host-and-deploy/iis/index)
* [<span data-ttu-id="61184-267">IIS modülleri genel bakış</span><span class="sxs-lookup"><span data-stu-id="61184-267">IIS Modules Overview</span></span>](https://docs.microsoft.com/iis/get-started/introduction-to-iis/iis-modules-overview)
* [<span data-ttu-id="61184-268">IIS 7.0 rolleri ve modülleri özelleştirme</span><span class="sxs-lookup"><span data-stu-id="61184-268">Customizing IIS 7.0 Roles and Modules</span></span>](https://technet.microsoft.com/library/cc627313.aspx)
* [<span data-ttu-id="61184-269">IIS`<system.webServer>`</span><span class="sxs-lookup"><span data-stu-id="61184-269">IIS `<system.webServer>`</span></span>](https://docs.microsoft.com/iis/configuration/system.webServer/)