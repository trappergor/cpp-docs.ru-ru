---
title: /DELAYLOAD (загрузка импорта с задержкой)
ms.date: 11/04/2016
f1_keywords:
- /delayload
- VC.Project.VCLinkerTool.DelayLoadDLLS
helpviewer_keywords:
- DELAYLOAD linker option
- -DELAYLOAD linker option
- /DELAYLOAD linker option
- delayed loading of DLLs, /DELAYLOAD option
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
ms.openlocfilehash: e92b470b7b5e76b39371f333cbbda150e7f6e8c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273364"
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (загрузка импорта с задержкой)

> **/ DELAYLOAD:**_dllname_

## <a name="parameters"></a>Параметры

*dllname*<br/>
Имя DLL-библиотеки, загрузку которой нужно задержать.

## <a name="remarks"></a>Примечания

При использовании параметра /DELAYLOAD DLL-библиотека, указанная с помощью `dllname`, загружается только при первом вызове функции этой DLL-библиотеки программой. Дополнительные сведения см. в разделе [поддержка компоновщика для Delay-Loaded DLLs](linker-support-for-delay-loaded-dlls.md). Можно использовать этот параметр сколько угодно раз, указывая сколько угодно DLL-библиотек. При компоновке программы нужно использовать Delayimp.lib. Также можно использовать собственную вспомогательную функцию загрузки с задержкой.

[/DELAY](delay-delay-load-import-settings.md) указывает настройки привязки и загрузки для каждой библиотеки DLL, загружаемых с задержкой.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. В **компоновщика** папку, выберите **ввода** страницу свойств.

1. Изменить **Отложенно загружаемые DLL** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
