---
title: "/FU (именование файла с принудительно используемым атрибутом #using) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.ForcedUsingFiles"
  - "/FU"
  - "VC.Project.VCNMakeTool.ForcedUsingAssemblies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FU - параметр компилятора [C++]"
  - "FU - параметр компилятора [C++]"
  - "-FU - параметр компилятора [C++]"
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FU (именование файла с принудительно используемым атрибутом #using)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Параметр компилятора, который можно использовать в качестве альтернативы передачи имени файла на [Директива \#using](../../preprocessor/hash-using-directive-cpp.md) в исходном коде.  
  
## Синтаксис  
  
```  
/FU file  
```  
  
## Аргументы  
 `file`  
 Определяет файл метаданных, на который будет создана ссылка в данной компиляции.  
  
## Заметки  
 Ключ \/FU имеет только одно имя файла.  Чтобы указать несколько файлов, используйте параметр \/FU каждое с одним.  
  
 При использовании [!INCLUDE[cppcli](../../build/reference/includes/cppcli_md.md)] и ссылки на метаданные для использования функции [Дружественных сборок](../../dotnet/friend-assemblies-cpp.md), нельзя использовать **\/FU**.  Необходимо добавить ссылку на метаданные в коде с помощью `#using`— вместе с атрибутом `[as friend]`.  Дружественных сборок не поддерживаются в [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)]\).  
  
 Дополнительные сведения о создании сборки или модуль \(CLR\) для среды CLR см. в разделе [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md).  Сведения о способах построения в [!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)] см. в разделе [Построение приложений и библиотек](../Topic/Building%20apps%20and%20libraries%20\(C++-CX\).md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Выберите папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Дополнительно**.  
  
4.  Измените значение свойства **Принудительное использование атрибута \#using**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>.  
  
## См. также  
 [Параметры выходного файла \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)