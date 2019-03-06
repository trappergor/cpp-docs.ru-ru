---
title: /ASSEMBLYMODULE (добавление модуля MSIL в сборку)
ms.date: 11/04/2016
f1_keywords:
- /assemblymodule
- VC.Project.VCLinkerTool.AddModuleNamesToAssembly
helpviewer_keywords:
- ASSEMBLYMODULE linker option
- assemblies [C++], adding modules to
- assemblies [C++]
- /ASSEMBLYMODULE linker option
- -ASSEMBLYMODULE linker option
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
ms.openlocfilehash: 567ec4b1e773e8aa4ff248c7bb110cfb594f089e
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416700"
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE (добавление модуля MSIL в сборку)

```
/ASSEMBLYMODULE:filename
```

## <a name="arguments"></a>Аргументы

*filename*<br/>
Модуль, который вы хотите включить в эту сборку.

## <a name="remarks"></a>Примечания

Параметр/ASSEMBLYMODULE позволяет добавлять ссылки на модуль в сборку. Сведения о типе в модуле не будут доступны для сборки программы, добавлена ссылка на модуль. Тем не менее сведения о типе в модуле будут доступны любой программе, которая ссылается на сборку.

Используйте [#using](../../preprocessor/hash-using-directive-cpp.md) добавлять ссылки на модуль в сборку и предоставления сведений о типе модуля сборки программы.

Например, рассмотрим следующий сценарий.

1. Создайте модуль с [/LN](../../build/reference/ln-create-msil-module.md).

1. Используйте добавившей в другом проекте, чтобы включить модуль в текущей компиляции, который создает сборку. Этот проект не будет ссылаться на модуль с помощью `#using`.

1. Любой проект, который ссылается на эту сборку, теперь можно использовать типы из модуля.

Доступны следующие параметры компоновщика, которые влияют на создание сборки.

- [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)

- [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

- [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

Компоновщик Visual C++ в качестве входных данных принимает NETMODULE-файлы, и выходной файл, создаваемый компоновщиком будет сборки или .netmodule с не зависят от времени выполнения на любом из netmodules-файлы, которые были введены в компоновщик.  Дополнительные сведения см. в разделе [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **ввода** страницу свойств.

1. Изменить **добавить модуль в сборку** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
