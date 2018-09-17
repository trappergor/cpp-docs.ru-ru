---
title: -KEYCONTAINER (задание контейнера ключей для подписи сборки) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
dev_langs:
- C++
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 850a8173dba3e69eaf52fdf174674e1dba58a4d8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723766"
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER (задание контейнера ключей для подписи сборки)

```
/KEYCONTAINER:name
```

## <a name="arguments"></a>Аргументы

*name*<br/>
Контейнер, содержащий ключ. Строку следует заключить в двойные кавычки (» «), если он содержит пробел.

## <a name="remarks"></a>Примечания

Компоновщик создает подписанную сборку, вставляя в манифест сборки открытый ключ и подписывая окончательную сборку закрытым ключом. Чтобы создать файл ключа, введите [sn -k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* в командной строке. **sn -i** устанавливает пару ключей в контейнер.

Если компиляция выполняется с [/LN](../../build/reference/ln-create-msil-module.md), имя файла ключа сохраняется в модуле и включается в сборку, которая создается при компиляции сборки, содержащей явную ссылку на модуль, с помощью [#using](../../preprocessor/hash-using-directive-cpp.md), или при связывании с [добавившей](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).

Можно также передать сведения о шифровании компилятору с помощью [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md). Используйте [/delaysign](../../build/reference/delaysign-partially-sign-an-assembly.md) Если требуется частично подписанную сборку. См. в разделе [сборки со строгими именами (подписывание сборок) (C + +/ CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) Дополнительные сведения о подписи сборки.

Доступны следующие параметры компоновщика, которые влияют на создание сборки.

- [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

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