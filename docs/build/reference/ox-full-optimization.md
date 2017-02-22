---
title: "/Ox (полная оптимизация) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.ToolOptimization"
  - "/ox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Ox - параметр компилятора [C++]"
  - "быстрый код"
  - "полная оптимизация"
  - "Ox - параметр компилятора [C++]"
  - "-Ox - параметр компилятора [C++]"
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /Ox (полная оптимизация)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Параметр компилятора **\/Ox** создает код, в котором скорость выполнения имеет приоритет над компактностью кода.  
  
## Синтаксис  
  
```  
/Ox  
```  
  
## Заметки  
 Задание параметра компилятора **\/Ox** дает тот же результат, что и использование следующих параметров.  
  
-   [Параметр \/Ob \(расширение встроенных функций\)](../../build/reference/ob-inline-function-expansion.md), где параметр варианта равен 2 \(**\/Ob2**\)  
  
-   [\/Og \(Виды глобальной оптимизации\)](../../build/reference/og-global-optimizations.md)  
  
-   [\/Oi \(создание встроенных функций\)](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md)  
  
-   [\/Ot \(приоритет скорости выполнения кода\)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)  
  
-   [\/Oy \(подавление указателей фрейма\)](../../build/reference/oy-frame-pointer-omission.md)  
  
 Параметр **\/Ox** несовместим со следующими параметрами:  
  
-   [\/O1 \(минимизировать размер\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)  
  
-   [\/O2 \(максимизировать скорость\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)  
  
-   [\/Od \(Выключение \(отладчика\)\)](../../build/reference/od-disable-debug.md)  
  
 Параметр компилятора **\/Ox** также включает оптимизацию именованных возвращаемых значений, после чего для стековых возвращаемых значений не используются конструкторы копирования и деструкторы.  Для получения дополнительной информации см. [\/O1, \/O2 \(минимизировать размер, максимизировать скорость\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md).  
  
 Можно отменить параметр компилятора **\/Ox**, если задать параметр **\/Oxs**, который сочетает параметр компилятора **\/Ox** с [\/Os \(приоритет небольшому размеру кода\)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md).  Объединенные параметры отдают приоритет меньшему размеру кода.  
  
 Как правило, следует задавать параметр [\/O2 \(максимизировать скорость\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) вместо **\/Ox** и [\/O1 \(минимизировать размер\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) вместо **\/Oxs**.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Перейдите на страницу свойств **Оптимизация**.  
  
4.  Измените значение свойства **Оптимизация**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.  
  
## См. также  
 [Параметры \/O \(оптимизация кода\)](../../build/reference/o-options-optimize-code.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)