---
title: -NOLOGO (отключение загрузочного объявления) (компоновщик) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
dev_langs:
- C++
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 405cfd08b681d8b48343bae5055f5be9cf23dadb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707581"
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