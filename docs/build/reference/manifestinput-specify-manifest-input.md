---
title: -MANIFESTINPUT (задание входных данных манифеста) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5259df2216a8c844123c308ece7ac6b0b650ab39
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705167"
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (задание входных данных манифеста)

Задает входной файл манифеста для включения в манифест, внедренный в изображение.

## <a name="syntax"></a>Синтаксис

```
/MANIFESTINPUT:filename
```

### <a name="parameters"></a>Параметры

*filename*<br/>
Файл манифеста для включения во встроенный манифест.

## <a name="remarks"></a>Примечания

**/MANIFESTINPUT** указывает путь к входного файла для создания внедренного манифеста в исполняемом образе. При наличии нескольких входных файлов манифеста, используйте параметр несколько раз — один раз для каждого входного файла. Входные файлы манифеста объединяются для создания внедренного манифеста. Этот параметр требует **/MANIFEST: ВНЕДРЕНИЕ** параметр.

Этот параметр нельзя установить непосредственно в Visual Studio. Вместо этого используйте **дополнительные файлы манифеста** свойства проекта, чтобы указать дополнительные файлы манифеста для включения. Дополнительные сведения см. в разделе [входные и выходные данные, инструмент манифеста, свойства конфигурации, \<имя_проекта > "диалогового окна" страницы свойств "](../../ide/input-and-output-manifest-tool.md).

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)