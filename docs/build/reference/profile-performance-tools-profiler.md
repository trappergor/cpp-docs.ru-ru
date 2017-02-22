---
title: "/PROFILE (профилировщик средств обеспечения производительности) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.Profile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/PROFILE - параметр компоновщика"
  - "-PROFILE - параметр компоновщика"
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /PROFILE (профилировщик средств обеспечения производительности)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает выходной файл, который может быть использован для профилировщика производительности инструментов.  
  
## Синтаксис  
  
```  
/PROFILE  
```  
  
## Заметки  
 \/PROFILE означает использование следующих параметров компоновщика:  
  
-   [\/OPT:REF](../../build/reference/opt-optimizations.md)  
  
-   \/OPT:NOICF  
  
-   [\/INCREMENTAL:NO](../../build/reference/incremental-link-incrementally.md)  
  
-   [\/FIXED:NO](../../build/reference/fixed-fixed-base-address.md)  
  
 Параметр \/PROFILE приводит к тому, что компоновщик создает раздел переадресации в образе программы.  Он позволяет профилировщику преобразовать образ программы, чтобы получить данные профилирования.  
  
 Использование параметра **\/PROFILE** доступно только в версиях Enterprise Edition.  Дополнительные сведения о PREfast см. в разделе [Общие сведения об анализе кода в C\/C\+\+](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните узел **Компоновщик**.  
  
4.  Выберите страницу свойств **Дополнительно**.  
  
5.  Измените значение свойства **Профилирование**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)