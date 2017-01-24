---
title: "Страницы свойств MIDL: Дополнительно | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCMidlTool.ErrorCheckBounds"
  - "VC.Project.VCMidlTool.ErrorCheckStubData"
  - "VC.Project.VCMidlTool.ErrorCheckAllocations"
  - "VC.Project.VCMidlTool.CPreprocessOptions"
  - "VC.Project.VCMidlTool.UndefinePreprocessorDefinitions"
  - "VC.Project.VCMidlTool.EnableErrorChecks"
  - "VC.Project.VCMidlTool.RedirectOutputAndErrors"
  - "VC.Project.VCMidlTool.ErrorCheckEnumRange"
  - "VC.Project.VCMidlTool.StructMemberAlignment"
  - "VC.Project.VCMidlTool.ErrorCheckRefPointers"
  - "VC.Project.VCMidlTool.ValidateParameters"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MIDL, страницы свойств"
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Страницы свойств MIDL: Дополнительно
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

На странице свойства **Дополнительно** в папке **MIDL** задаются следующие параметры компилятора MIDL:  
  
-   Включение проверок ошибок \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Проверка распределения \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Проверки допустимости \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Проверка диапазона перечисления \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Проверка ссылочных указателей \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Проверка данных заглушки \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   Проверка параметров \([\/robust](http://msdn.microsoft.com/library/windows/desktop/aa367363)\) \*  
  
-   Выравнивание элемента структуры \([\/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388)\)  
  
-   Перенаправление вывода \([\/o](http://msdn.microsoft.com/library/windows/desktop/aa367351)\)  
  
-   Параметры C\-процессов \([\/cpp\_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318)\)  
  
-   Отмена определений препроцессора \([\/U](http://msdn.microsoft.com/library/windows/desktop/aa367373)\)  
  
 \* \/robust — только для использования при построении для Windows 2000 или для машин более поздней версии.  Если создается проект ATL, и необходимо использовать \/robust, измените эту строку в файле dlldatax.c:  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 Сведения о том, как получить доступ к странице свойства **Дополнительно** в папке **MIDL**, см. раздел [Практическое руководство. Задание свойств проекта при помощи страниц свойств](../Topic/How%20to:%20Specify%20Project%20Properties%20with%20Property%20Pages.md).  
  
 Сведения о программном доступе к параметрам MIDL для проектов C\+\+ см. в разделе <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.  
  
## См. также  
 [Страницы свойств MIDL](../ide/midl-property-pages.md)