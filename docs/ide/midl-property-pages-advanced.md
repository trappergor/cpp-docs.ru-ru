---
title: 'Страницы свойств MIDL: "Дополнительно" |Документы Майкрософт'
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
ms.openlocfilehash: 9b99dae277fec7618c2e7caeb76229edce7a78c2
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207764"
---
# <a name="midl-property-pages-advanced"></a>Страницы свойств MIDL: Дополнительно
Страница свойств **Дополнительно** в папке **MIDL** указывает следующие параметры компилятора MIDL:  
  
-   Разрешить проверку ошибок ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Проверка ошибок нехватки памяти ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Проверка границ ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Проверка границ перечислений ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Проверка указателей ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Проверках данных-заглушек ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Проверка параметров ([/robust](http://msdn.microsoft.com/library/windows/desktop/aa367363)) \*  
  
-   Выравнивание членов структур ([/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388))  
  
-   Перенаправить вывод ([/o](http://msdn.microsoft.com/library/windows/desktop/aa367351))  
  
-   Параметры препроцессора C ([/cpp_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318))  
  
-   Отменить определения препроцессора ([/U](http://msdn.microsoft.com/library/windows/desktop/aa367373))  
  
 \* /robust предназначен для использования только при сборке для компьютера с Windows 2000 или более поздней версии. Если вы выполняете сборку проекта ATL и хотите использовать /robust, измените следующую строку в файле dlldatax.c:  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 Сведения о доступе к странице свойств **Дополнительно** в папке **MIDL** см. в разделе [Работа со свойствами проектов](../ide/working-with-project-properties.md).  
  
 Сведения о программном доступе к параметрам MIDL для проектов C++ см. в разделе <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств MIDL](../ide/midl-property-pages.md)