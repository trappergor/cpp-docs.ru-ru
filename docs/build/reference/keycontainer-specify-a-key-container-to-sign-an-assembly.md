---
title: /KEYCONTAINER (задание контейнера ключей для подписи сборки)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
ms.openlocfilehash: 96d2f5fed0e450224f82ee909cea9d56082505fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291617"
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

Если компиляция выполняется с [/LN](ln-create-msil-module.md), имя файла ключа сохраняется в модуле и включается в сборку, которая создается при компиляции сборки, содержащей явную ссылку на модуль, с помощью [#using](../../preprocessor/hash-using-directive-cpp.md), или при связывании с [добавившей](assemblymodule-add-a-msil-module-to-the-assembly.md).

Можно также передать сведения о шифровании компилятору с помощью [/keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md). Используйте [/delaysign](delaysign-partially-sign-an-assembly.md) Если требуется частично подписанную сборку. См. в разделе [сборки со строгими именами (подписывание сборок) (C++выполняет)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) Дополнительные сведения о подписи сборки.

Доступны следующие параметры компоновщика, которые влияют на создание сборки.

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

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
