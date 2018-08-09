---
title: Ресурсы манифеста | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifest resources
- resources [Visual Studio], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1546beabadda06c5433450f67e340eaaabb0aa26
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012278"
---
# <a name="manifest-resources"></a>Ресурсы манифеста
Ресурсы манифеста — это XML-файлы, описывающие зависимости, которые использует приложение. Например, в Visual Studio файл манифеста, созданный мастером MFC, определяет, какие версии библиотек DLL общих элементов управления Windows (5.0 или 6.0), приложение должно использовать:  
  
```xml  
<description>Your app description here</description>   
<dependency>   
    <dependentAssembly>   
        <assemblyIdentity   
            type="win32"   
            name="Microsoft.Windows.Common-Controls"   
            version="6.0.0.0"   
            processorArchitecture="X86"   
            publicKeyToken="6595b64144ccf1df"   
            language="*"   
        />   
    </dependentAssembly>   
</dependency>   
```  
  
 Для приложений Windows XP и Windows Vista ресурс манифеста не только определяет, что приложение должно использовать последнюю версию общих элементов управления Windows (версии 6.0, см. выше), но также поддерживает [элемент управления Syslink](http://msdn.microsoft.com/library/windows/desktop/bb760706).  
  
 Чтобы узнать версию и введите сведения, содержащиеся в ресурсе манифеста, можно открыть файл в средстве просмотра XML или в Visual Studio [текстовый редактор](http://msdn.microsoft.com/508e1f18-99d5-48ad-b5ad-d011b21c6ab1). Дополнительные сведения см. в статье [Открытие ресурса манифеста в текстовом редакторе Visual Studio](../windows/how-to-open-a-manifest-resource.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. . Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе  [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
## <a name="limitations"></a>Ограничения  
 Допускается иметь только один ресурс манифеста на каждый модуль.  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Элементы управления](../mfc/controls-mfc.md)   
 [Работа с файлами ресурсов](../windows/working-with-resource-files.md)