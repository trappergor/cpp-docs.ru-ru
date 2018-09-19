---
title: -DELAYLOAD (Импорт отложенной загрузки) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /delayload
- VC.Project.VCLinkerTool.DelayLoadDLLS
dev_langs:
- C++
helpviewer_keywords:
- DELAYLOAD linker option
- -DELAYLOAD linker option
- /DELAYLOAD linker option
- delayed loading of DLLs, /DELAYLOAD option
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 800b3d7d588d1038ac61cb7c9c4b9f1913bec9d4
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722375"
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (загрузка импорта с задержкой)

> **/ DELAYLOAD:**_dllname_

## <a name="parameters"></a>Параметры

*dllname*<br/>
Имя DLL-библиотеки, загрузку которой нужно задержать.

## <a name="remarks"></a>Примечания

При использовании параметра /DELAYLOAD DLL-библиотека, указанная с помощью `dllname`, загружается только при первом вызове функции этой DLL-библиотеки программой. Дополнительные сведения см. в разделе [поддержка компоновщика для Delay-Loaded DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md). Можно использовать этот параметр сколько угодно раз, указывая сколько угодно DLL-библиотек. При компоновке программы нужно использовать Delayimp.lib. Также можно использовать собственную вспомогательную функцию загрузки с задержкой.

[/DELAY](../../build/reference/delay-delay-load-import-settings.md) указывает настройки привязки и загрузки для каждой библиотеки DLL, загружаемых с задержкой.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

2. В **компоновщика** папку, выберите **ввода** страницу свойств.

3. Изменить **Отложенно загружаемые DLL** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)