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
ms.openlocfilehash: 728e8a84ff8d1afac99f99dbb975c7fd9360bcc1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815259"
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

1. Создайте модуль с [/LN](ln-create-msil-module.md).

1. Используйте добавившей в другом проекте, чтобы включить модуль в текущей компиляции, который создает сборку. Этот проект не будет ссылаться на модуль с помощью `#using`.

1. Любой проект, который ссылается на эту сборку, теперь можно использовать типы из модуля.

Доступны следующие параметры компоновщика, которые влияют на создание сборки.

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

Компоновщик MSVC в качестве входных данных принимает NETMODULE-файлы и выходной файл, создаваемый компоновщиком будет сборки или .netmodule с не зависят от времени выполнения на любом из netmodules-файлы, которые были введены в компоновщик.  Дополнительные сведения см. в разделе [NETMODULE-файлы в качестве входных файлов компоновщика](netmodule-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **ввода** страницу свойств.

1. Изменить **добавить модуль в сборку** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
