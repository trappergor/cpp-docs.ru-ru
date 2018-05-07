---
title: 'Страницы свойств MIDL: Дополнительно | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ValidateParameters
dev_langs:
- C++
helpviewer_keywords:
- MIDL, property pages
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f87518c23848cea91a3e3c48361aa0a63fa88a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="midl-property-pages-advanced"></a>Страницы свойств MIDL: Дополнительно
**Дополнительно** на странице свойств в **MIDL** папки задаются следующие параметры компилятора MIDL:  
  
-   Включить проверку ошибок ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Проверка распределения ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Проверки допустимости ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Проверка границ перечислений ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Проверка ссылочных указателей ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Проверка данных заглушки ([/Error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Проверка параметров ([/ robust](http://msdn.microsoft.com/library/windows/desktop/aa367363)) *  
  
-   Выравнивание члена структуры ([/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388))  
  
-   Перенаправлять выходные данные ([/o](http://msdn.microsoft.com/library/windows/desktop/aa367351))  
  
-   Параметры предварительной обработки C ([/cpp_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318))  
  
-   Отменить определения препроцессора ([/U](http://msdn.microsoft.com/library/windows/desktop/aa367373))  
  
 \* / robust предназначен только для использования при построении для Windows 2000 или более поздней версии. При построении проекта ATL и хотите использовать / robust, измените следующую строку в файле dlldatax.c:  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 Сведения о доступе к **Дополнительно** на странице свойств в **MIDL** папку, в разделе [работа со свойствами проекта](../ide/working-with-project-properties.md).  
  
 Сведения о том, как получить программный доступ к параметрам MIDL для проектов C++ см. в разделе <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств MIDL](../ide/midl-property-pages.md)