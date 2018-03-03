---
title: "Доступ к сведениям о версии из создаваемой программы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.version
dev_langs:
- C++
helpviewer_keywords:
- VerQueryValue
- version information, accessing from within programs
- GetFileVersionInfo
- version information
ms.assetid: 18622333-d9e8-4309-9465-677cd10c79b1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e9d47a4df27333afc5d267e791e20d1ed4fe8430
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="accessing-version-information-from-within-your-program"></a>Доступ к сведениям о версии из создаваемой программы
### <a name="to-access-version-information-from-within-your-program"></a>Доступ к сведениям о версии из создаваемой программы  
  
1.  Если нужно получить доступ к сведениям о версии из создаваемой программы, используйте функции [GetFileVersionInfo](http://msdn.microsoft.com/library/windows/desktop/ms647003.aspx) и [VerQueryValue](http://msdn.microsoft.com/library/windows/desktop/ms647464.aspx) .  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 **Требования**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редактор сведений о версии](../windows/version-information-editor.md)   
 [Сведения о версии (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)

