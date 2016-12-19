---
title: "/LN (создание модуля MSIL) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/LN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LN - параметр компилятора [C++]"
  - "-LN - параметр компилятора [C++]"
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /LN (создание модуля MSIL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает, что манифест сборки не следует вставлять в файл вывода.  
  
## Синтаксис  
  
```  
/LN  
```  
  
## Заметки  
 По умолчанию параметр **\/LN** не действует \(манифест сборки вставлен в файл вывода\).  
  
 При использовании параметра **\/LN** следует также использовать один из параметров [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Модулем называется управляемая программа, не имеющая метаданных сборки в манифесте.  При использовании в компиляции параметров [Параметр \/c \(компиляция без связывания\)](../../build/reference/c-compile-without-linking.md) и **\/LN** следует задать параметр [\/NOASSEMBLY \(создать модуль MSIL\)](../../build/reference/noassembly-create-a-msil-module.md) в стадии компоновщика, чтобы создать файл вывода.  
  
 Возможно, потребуется создать модули, если к построению сборок необходим подход на основе компонента.  То есть можно составлять типы и компилировать их в модули.  Также можно создать сборку из одного или нескольких модулей.  Дополнительные сведения о создании сборок из модулей см. в разделах [.NETMODULE\-файлы в качестве входных файлов компоновщика](../Topic/.netmodule%20Files%20as%20Linker%20Input.md) или [Al.exe \(компоновщик сборок\)](../Topic/Al.exe%20\(Assembly%20Linker\).md).  
  
 Расширение файла по умолчанию для модуля .netmodule.  
  
 В выпусках [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] до Visual C\+\+ 2005 модуль создавался с помощью **\/clr:noAssembly**.  
  
 Компоновщик Visual C\+\+ принимает файлы .netmodule как входной и выходной файл, созданный компоновщиком будут сборкой или .netmodule без времени выполнения зависимости на любом .netmodules, созданных входным компоновщику.  Для получения дополнительной информации см. [.NETMODULE\-файлы в качестве входных файлов компоновщика](../Topic/.netmodule%20Files%20as%20Linker%20Input.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
-   Следует задать в фазе компоновщика параметр [\/NOASSEMBLY \(создать модуль MSIL\)](../../build/reference/noassembly-create-a-msil-module.md), чтобы создать файл вывода.  
  
### Установка данного параметра компилятора программным способом  
  
-   Этот параметр компилятора нельзя изменить программным способом.  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)