---
title: "/GZ (Позволяет проверку фрейма стека ошибки во время выполнения) | Microsoft Docs"
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
  - "/gz"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GZ - параметр компилятора [C++]"
  - "отладочные построения, перехват ошибок построения выпуска"
  - "GZ - параметр компилятора [C++]"
  - "-GZ - параметр компилятора [C++]"
  - "ошибки построения выпуска"
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GZ (Позволяет проверку фрейма стека ошибки во время выполнения)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет такие же операции, как и параметр [\/RTC \(проверки ошибок во время выполнения\)](../../build/reference/rtc-run-time-error-checks.md).  Устаревший.  
  
## Синтаксис  
  
```  
/GZ  
```  
  
## Заметки  
 **\/GZ** только для использования в неоптимизированном построении \([\/Od \(Выключение \(отладчика\)\)](../../build/reference/od-disable-debug.md)\).  
  
 Параметр **\/GZ** использовать не рекомендуется; вместо него следует использовать [\/RTC \(проверки ошибок во время выполнения\)](../../build/reference/rtc-run-time-error-checks.md).  Для получения дополнительной информации см. [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ru-ru/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Введите параметры компилятора в поле **Дополнительные параметры**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)