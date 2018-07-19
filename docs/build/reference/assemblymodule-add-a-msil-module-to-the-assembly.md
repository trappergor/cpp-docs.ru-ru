---
title: -ASSEMBLYMODULE (Добавление модуля MSIL в сборку) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /assemblymodule
- VC.Project.VCLinkerTool.AddModuleNamesToAssembly
dev_langs:
- C++
helpviewer_keywords:
- ASSEMBLYMODULE linker option
- assemblies [C++], adding modules to
- assemblies [C++]
- /ASSEMBLYMODULE linker option
- -ASSEMBLYMODULE linker option
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f408bcf58808f64c652f0b1715c47aba7237c160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373859"
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE (добавление модуля MSIL в сборку)
```  
/ASSEMBLYMODULE:filename  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *filename*  
 Модуль, который требуется включить в этой сборке.  
  
## <a name="remarks"></a>Примечания  
 Параметр/ASSEMBLYMODULE позволяет добавлять ссылки на модуль в сборку. Сведения о типе в модуле будет недоступен для программы сборки, добавившей ссылку на модуль. Тем не менее сведения о типе в модуле будут доступны любой программе, которая ссылается на сборку.  
  
 Используйте [#using](../../preprocessor/hash-using-directive-cpp.md) добавлять ссылки на модуль в сборку и предоставления сведений о типе модуля программе сборки.  
  
 Например, рассмотрим следующий сценарий.  
  
1.  Создание модуля с [/LN](../../build/reference/ln-create-msil-module.md).  
  
2.  Используйте/ASSEMBLYMODULE в другом проекте, чтобы включить модуль в текущей компиляции, что приведет к созданию сборки. Этот проект не будет ссылаться на модуль с `#using`.  
  
3.  Любой проект, который ссылается на эту сборку, теперь можно использовать типы из модуля.  
  
 Доступны следующие параметры компоновщика, влияющие на создание сборки.  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
-   [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Компоновщик Visual C++ в качестве входных данных принимает NETMODULE-файлы и будет выходной файл, создаваемый компоновщиком, сборка или NETMODULE-файл с не зависят от времени выполнения на любом netmodules-файлы, которые были введены в компоновщик.  Дополнительные сведения см. в разделе [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **ввода** страницу свойств.  
  
4.  Изменить **добавить модуль в сборку** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)