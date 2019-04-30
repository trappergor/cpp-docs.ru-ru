---
title: /ASSEMBLYRESOURCE (внедрение управляемого ресурса)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.EmbedManagedResourceFile
- /ASSEMBLYRESOURCE
helpviewer_keywords:
- ASSEMBLYRESOURCE linker option
- assemblies [C++]
- -ASSEMBLYRESOURCE linker option
- assemblies [C++], linking resource files
- /ASSEMBLYRESOURCE linker option
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
ms.openlocfilehash: 1eac489ffd01f6bd79fc8c5bbda23adb751c9486
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295075"
---
# <a name="assemblyresource-embed-a-managed-resource"></a>/ASSEMBLYRESOURCE (внедрение управляемого ресурса)

```
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]
```

## <a name="parameters"></a>Параметры

*filename*<br/>
Управляемый ресурс, который требуется внедрить в этой сборке.

*name*<br/>
Необязательный параметр. Логическое имя ресурса; имя, используемое для загрузки ресурса. По умолчанию используется имя файла.

Кроме того можно указать, если этот файл должен быть закрытым в манифесте сборки. По умолчанию *имя* является открытым в сборке.

## <a name="remarks"></a>Примечания

Используйте параметр/ASSEMBLYRESOURCE для внедрения ресурса в сборке.

Ресурсы в сборку при создании с ключом компоновщика открыты. Компоновщик не поддерживает переименование ресурса в сборке.

Если *filename* является файлом ресурсов (RESOURCES) платформы .NET Framework, созданным, например, по [генератор файлов ресурсов (Resgen.exe)](/dotnet/framework/tools/resgen-exe-resource-file-generator) или в среде разработки, он может осуществляться с помощью членов пространства **System.Resources** пространства имен (см. в разделе [System.Resources.ResourceManager](/dotnet/api/system.resources.resourcemanager) Дополнительные сведения). Все прочие ресурсы, используйте **GetManifestResource** \* методы в **System.Reflection.Assembly** класс для доступа к ресурсу во время выполнения.

Доступны следующие параметры компоновщика, которые влияют на создание сборки.

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **ввода** страницу свойств.

1. Изменить **внедренный файл управляемых ресурсов** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
