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
ms.openlocfilehash: 0ef0c6f8e0073e7450daa8d0433ce4d6e82ceab8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320530"
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (отмена вывода начального заголовка) (Компоновщик)

```
/NOLOGO
```

## <a name="remarks"></a>Примечания

Параметр/nologo не отображать уведомление об авторских правах и номере версии.

Этот параметр также подавляет вывод из файлов команд. Дополнительные сведения см. в разделе [командные файлы LINK](linking.md).

По умолчанию эта информация отправляется компоновщиком в окно вывода. В командной строке он отправляется в стандартный вывод и могут быть перенаправлены в файл.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Этот параметр должен использоваться только из командной строки.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. Этот параметр не может изменяться программно.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
