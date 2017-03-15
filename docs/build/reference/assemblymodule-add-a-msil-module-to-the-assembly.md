---
title: "/ASSEMBLYMODULE (добавление модуля MSIL в сборку) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/assemblymodule"
  - "VC.Project.VCLinkerTool.AddModuleNamesToAssembly"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYMODULE - параметр компоновщика"
  - "сборки [C++]"
  - "сборки [C++], добавление модулей"
  - "ASSEMBLYMODULE - параметр компоновщика"
  - "-ASSEMBLYMODULE - параметр компоновщика"
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /ASSEMBLYMODULE (добавление модуля MSIL в сборку)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYMODULE:filename  
```  
  
## Заметки  
 Здесь:  
  
 *filename*  
 Модуль для включения в данную сборку.  
  
## Заметки  
 Параметр \/ASSEMBLYMODULE разрешает добавление ссылки модуля в сборку.  Сведения о типе в модуле будут недоступны программе сборки, добавившей ссылку на модуль.  Однако сведения о типе в модуле будут доступны любой программе, содержащей ссылку на сборку.  
  
 Параметр [\#using](../../preprocessor/hash-using-directive-cpp.md) можно использовать как для добавления ссылки на модуль в сборку, так и для предоставления ассемблеру доступа к сведениям о типе модуля.  
  
 Например, можно рассмотреть следующий скрипт:  
  
1.  Создание модуля с параметром [\/LN](../../build/reference/ln-create-msil-module.md).  
  
2.  Параметр \/ASSEMBLYMODULE следует использовать в другом проекте, чтобы включить модуль в текущую компиляцию, создающую сборку.  Данный проект не будет ссылаться на модуль с параметром `#using`.  
  
3.  Любой проект, который ссылается на данную сборку, будет также использовать типы из модуля.  
  
 Ниже перечислены прочие параметры компоновщика, влияющие на создание сборок:  
  
-   [\/ASSEMBLYDEBUG](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Компоновщик Visual C\+\+ принимает файлы .netmodule как входной и выходной файл, созданный компоновщиком будут сборкой или .netmodule без времени выполнения зависимости на любом .netmodules, созданных входным компоновщику.  Для получения дополнительной информации см. [.NETMODULE\-файлы в качестве входных файлов компоновщика](../Topic/.netmodule%20Files%20as%20Linker%20Input.md).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Ввод**.  
  
4.  Измените значение свойства **Добавление модуля к сборке**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)