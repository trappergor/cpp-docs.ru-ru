---
title: -DEBUGTYPE (параметры отладочных сведений) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /debugtype
dev_langs:
- C++
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98edb5945c2cf01d90cd5dae1a750c0fdd37757f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723285"
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE (параметры отладочных сведений)

Параметр /DEBUGTYPE указывает типы отладочной информации, создаваемой при использовании параметра /Debug.

```
/DEBUGTYPE:[CV | PDATA | FIXUP]
```

## <a name="arguments"></a>Аргументы

**ПЕРЕКРЕСТНОЙ ПРОВЕРКИ**<br/>
Указывает компоновщику выводить отладочную информацию для символов, номеров строк и другие сведения о компиляции объектов в PDB-файл. По умолчанию этот параметр включен при **/DEBUG** указан и **/DEBUGTYPE** не указан.

**PDATA**<br/>
Указывает компоновщику добавить записи PDATA и XDATA в поток отладочной информации в PDB-файле. По умолчанию этот параметр включен при как **/DEBUG** и **/Driver** параметров. Если **/DEBUGTYPE:PDATA** указан сам по себе, компоновщик автоматически включает символы отладки в PDB-файл. Если **/DEBUGTYPE:PDATA, адресная ПРИВЯЗКА** указан, компоновщик не включает символы отладки в PDB-файл.

**АДРЕСНАЯ ПРИВЯЗКА**<br/>
Указывает компоновщику добавить записи таблицы перемещений в поток отладочной информации в PDB-файле. По умолчанию этот параметр включен при как **/DEBUG** и **/PROFILE** параметров. Если **/DEBUGTYPE:FIXUP** или **/DEBUGTYPE:FIXUP PDATA** указан, компоновщик не включает символы отладки в PDB-файл.

Аргументы для **/DEBUGTYPE** можно объединять в любом порядке, разделив их запятыми. **/DEBUGTYPE** параметр и его аргументы не учитывается регистр.

## <a name="remarks"></a>Примечания

Используйте **/DEBUGTYPE** параметр, чтобы указать Включение перемещения данных или pdata и xdata информация заголовка таблицы в потоке отладки. В этом случае компоновщик включает сведения о коде пользовательского режима, который видим в отладчике ядра при остановке в коде режима ядра. Чтобы сделать символы отладки доступными при **адресная ПРИВЯЗКА** будет указано, включают **CV** аргумент.

Для отладки кода в пользовательском режиме, который является типичным для приложений, **/DEBUGTYPE** параметр не требуется. По умолчанию выходные параметры компилятора, укажите отладки ([/Z7, / Zi, /ZI](../../build/reference/z7-zi-zi-debug-information-format.md)) выдавать все сведения о необходимости средой Visual Studio отладчика. Используйте **/DEBUGTYPE:PDATA** или **/DEBUGTYPE:CV, PDATA адресная ПРИВЯЗКА** для отладки код, который сочетает в себе компоненты пользовательского режима и режима ядра, например приложения настройки для драйвера устройства. Дополнительные сведения об отладчиках режима ядра см. в разделе [отладки средства для Windows (WinDbg, KD, CDB, NTSD)](/windows-hardware/drivers/debugger/index)

## <a name="see-also"></a>См. также

[/ DEBUG (создать отладочную информацию)](../../build/reference/debug-generate-debug-info.md)
[/Driver (драйвер режима ядра Windows NT)](../../build/reference/driver-windows-nt-kernel-mode-driver.md)
[/Profile (Profiler средства производительности)](../../build/reference/profile-performance-tools-profiler.md) 
 [Средства отладки для Windows (WinDbg, KD, CDB, NTSD)](/windows-hardware/drivers/debugger/index)