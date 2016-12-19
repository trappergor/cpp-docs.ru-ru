---
title: "/arch (ARM) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /arch (ARM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает архитектуру для создания кода на платформе ARM.  См. также [\/arch \(x86\)](../../build/reference/arch-x86.md) и [\/arch \(x64\)](../../build/reference/arch-x64.md).  
  
## Синтаксис  
  
```  
/arch:[ARMv7VE|VFPv4]  
```  
  
## Аргументы  
 **\/arch:ARMv7VE**  
 Включает использование инструкций расширения виртуализации ARMv7VE.  
  
 **\/arch:VFPv4**  
 Включает использование инструкций ARM VFPv4.  Если этот параметр не указан, по умолчанию используется VFPv3.  
  
## Заметки  
 Макрос `_M_ARM_FP` \(только для ARM\) указывает, какой был использован параметр компилятора **\/arch**.  Для получения дополнительной информации см. [Предустановленный макрос](../../preprocessor/predefined-macros.md).  
  
 При компиляции с помощью [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) параметр **\/arch** не оказывает влияния на создание кода для управляемых функций.  **\/arch** влияет только на создание кода для собственных функций.  
  
### Чтобы задать параметр компилятора \/arch:ARMv7VE или \/arch:VFPv4 в Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Для получения дополнительной информации см. [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Выберите папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  В диалоговом окне **Дополнительные параметры** добавьте `/arch:ARMv7VE` или `/arch:VFPv4`.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## См. также  
 [\/arch \(минимальная архитектура ЦП\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)