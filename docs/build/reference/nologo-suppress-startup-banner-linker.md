---
title: /NOLOGO (отмена вывода начального заголовка) (Компоновщик)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
ms.openlocfilehash: d246da2e10f7c16f7c194962841e2e44d1fd1758
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515548"
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (отмена вывода начального заголовка) (Компоновщик)

```
/NOLOGO
```

## <a name="remarks"></a>Примечания

Параметр/nologo не отображать уведомление об авторских правах и номере версии.

Этот параметр также подавляет вывод из файлов команд. Дополнительные сведения см. в разделе [командные файлы LINK](../../build/reference/link-command-files.md).

По умолчанию эта информация отправляется компоновщиком в окно вывода. В командной строке он отправляется в стандартный вывод и могут быть перенаправлены в файл.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Этот параметр должен использоваться только из командной строки.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. Этот параметр не может изменяться программно.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)