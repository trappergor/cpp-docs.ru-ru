---
title: -NOENTRY (точка входа отсутствует) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
dev_langs:
- C++
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd90cb7824050e9bd0110e75f7120c4f004b8b47
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713470"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (точка входа отсутствует)

```
/NOENTRY
```

## <a name="remarks"></a>Примечания

Параметр /NOENTRY требуется для создания DLL-библиотеки, содержащей только ресурсы, без исполняемого кода. Дополнительные сведения см. в разделе [Создание библиотеки DLL Resource-Only](../../build/creating-a-resource-only-dll.md).

Используйте этот параметр, чтобы LINK не добавлял ссылку на `_main` в DLL.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **Дополнительно** страницу свойств.

1. Изменить **нет точки входа** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>.

## <a name="see-also"></a>См. также

[Создание библиотек DLL, содержащих только ресурсы](../../build/creating-a-resource-only-dll.md)<br/>
[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)