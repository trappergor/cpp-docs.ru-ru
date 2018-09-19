---
title: -ASSEMBLYLINKRESOURCE (ссылка на ресурс .NET Framework) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
dev_langs:
- C++
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36f8f6adcfe5d67b3d27b8557627725ba7295829
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704149"
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>Параметр /ASSEMBLYLINKRESOURCE (ссылка на ресурс .NET Framework)

```
/ASSEMBLYLINKRESOURCE:filename
```

## <a name="arguments"></a>Аргументы

*filename*<br/>
Файл ресурсов .NET Framework, ссылку на который необходимо создать из сборки.

## <a name="remarks"></a>Примечания

Параметр этом случае создает ссылку на ресурс .NET Framework в выходном файле; файл ресурса не помещается в выходной файл. [/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) внедряет файл ресурсов в выходной файл.

Связанные ресурсы являются открытыми в сборке при создании с ключом компоновщика.

/ ASSEMBLYLINKRESOURCE требует, компиляция [/CLR](../../build/reference/clr-common-language-runtime-compilation.md); [/LN](../../build/reference/ln-create-msil-module.md) или [/NOASSEMBLY предписывает](../../build/reference/noassembly-create-a-msil-module.md) не допускается в этом случае.

Если *filename* является файлом ресурсов .NET Framework, созданным, например, по [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) или в среде разработки, он может осуществляться с помощью членов пространства **System.Resources** пространства имен. Дополнительные сведения см. в разделе [System.Resources.ResourceManager](https://msdn.microsoft.com/library/system.resources.resourcemanager.aspx). Все прочие ресурсы, используйте **GetManifestResource** \* методы в **System.Reflection.Assembly** класс для доступа к ресурсу во время выполнения.

*Имя файла* может иметь любой формат файла. Например может потребоваться сделать собственную библиотеку DLL частью сборки, поэтому его можно установить в глобальный кэш сборок и доступна из управляемого кода в сборке.

Доступны следующие параметры компоновщика, которые влияют на создание сборки.

- [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)