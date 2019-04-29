---
title: Параметр /ASSEMBLYLINKRESOURCE (ссылка на ресурс .NET Framework)
ms.date: 11/04/2016
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
ms.openlocfilehash: fb707a2721ed40ee3ec37d01b2bbcfcc51f05c38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295166"
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>Параметр /ASSEMBLYLINKRESOURCE (ссылка на ресурс .NET Framework)

```
/ASSEMBLYLINKRESOURCE:filename
```

## <a name="arguments"></a>Аргументы

*filename*<br/>
Файл ресурсов .NET Framework, ссылку на который необходимо создать из сборки.

## <a name="remarks"></a>Примечания

Параметр этом случае создает ссылку на ресурс .NET Framework в выходном файле; файл ресурса не помещается в выходной файл. [/ ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) внедряет файл ресурсов в выходной файл.

Связанные ресурсы являются открытыми в сборке при создании с ключом компоновщика.

/ ASSEMBLYLINKRESOURCE требует, компиляция [/CLR](clr-common-language-runtime-compilation.md); [/LN](ln-create-msil-module.md) или [/NOASSEMBLY предписывает](noassembly-create-a-msil-module.md) не допускается в этом случае.

Если *filename* является файлом ресурсов .NET Framework, созданным, например, по [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) или в среде разработки, он может осуществляться с помощью членов пространства **System.Resources** пространства имен. Дополнительные сведения см. в разделе [System.Resources.ResourceManager](/dotnet/api/system.resources.resourcemanager). Все прочие ресурсы, используйте **GetManifestResource** \* методы в **System.Reflection.Assembly** класс для доступа к ресурсу во время выполнения.

*Имя файла* может иметь любой формат файла. Например может потребоваться сделать собственную библиотеку DLL частью сборки, поэтому его можно установить в глобальный кэш сборок и доступна из управляемого кода в сборке.

Доступны следующие параметры компоновщика, которые влияют на создание сборки.

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
