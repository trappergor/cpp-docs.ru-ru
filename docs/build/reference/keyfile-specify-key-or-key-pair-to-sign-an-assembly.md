---
title: -KEYFILE (задание ключа или пары ключей для подписи сборки) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /keyfile
- VC.Project.VCLinkerTool.KeyFile
dev_langs:
- C++
helpviewer_keywords:
- /KEYFILE linker option
- -KEYFILE linker option
- KEYFILE linker option
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f43609e14d4e081f39c43cb8e548b8b6ac7923a1
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701278"
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE (задание ключа или пары ключей для подписи сборки)

```
/KEYFILE:filename
```

## <a name="arguments"></a>Аргументы

*filename*<br/>
Файл, содержащий ключ. Строку следует заключить в двойные кавычки (» «), если он содержит пробел.

## <a name="remarks"></a>Примечания

Компоновщик вставляет открытый ключ в манифест сборки и затем подписывает окончательную сборку закрытым ключом. Чтобы создать файл ключа, введите [sn -k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* в командной строке. Считается, что подписанная сборка имеет строгое имя.

Если компиляция выполняется с [/LN](../../build/reference/ln-create-msil-module.md), имя файла ключа сохраняется в модуле и включается в сборку, которая создается при компиляции сборки, содержащей явную ссылку на модуль, с помощью [#using](../../preprocessor/hash-using-directive-cpp.md), или при связывании с [добавившей](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).

Можно также передать сведения о шифровании для компоновщика [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md). Используйте [/delaysign](../../build/reference/delaysign-partially-sign-an-assembly.md) Если требуется частично подписанную сборку. См. в разделе [сборки со строгими именами (подписывание сборок) (C + +/ CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) Дополнительные сведения о подписи сборки.

Одновременно **/keyfile** и **/keycontainer** указаны (в командной строке или с помощью настраиваемого атрибута), компоновщик сначала попытаются использовать контейнер ключей. В случае успеха сборка подписывается данными контейнера ключей. Если компоновщику не удается найти контейнер ключей, он попытается файл, заданный параметром/keyfile. В случае успеха сборка подписывается данными из файла ключей, и эти данные о ключах будут помещены в контейнер ключей (аналогично команде sn -i); таким образом, при следующей компиляции контейнер ключей будет действителен.

Обратите внимание, что файл ключей может содержать только открытый ключ.

См. в разделе [Создание и использование сборок со строгими именами](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies) Дополнительные сведения о подписи сборки.

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