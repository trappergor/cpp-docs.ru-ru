---
title: Константы атрибутов файлов
ms.date: 11/04/2016
f1_keywords:
- A_HIDDEN
- _A_NORMAL
- _A_SUBDIR
- _A_RDONLY
- A_NORMAL
- A_SUBDIR
- _A_SYSTEM
- c.constants.file
- _A_HIDDEN
- A_RDONLY
- _A_ARCH
- A_ARCH
helpviewer_keywords:
- constants [C++], file attributes
- file attribute constants [C++]
- _A_SYSTEM constant
- files [C++], file attribute constants
- _A_SUBDIR constant
- _A_ARCH constant
- _A_NORMAL constant
- _A_HIDDEN constant
- _A_RDONLY constant
ms.assetid: 8dc8ccb9-99f5-446b-876c-7ebecc2f764f
ms.openlocfilehash: 271459c33cdcc1110222871bdca06d3f04edb497
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750888"
---
# <a name="file-attribute-constants"></a>Константы атрибутов файлов

## <a name="syntax"></a>Синтаксис

```
#include <io.h>
```

## <a name="remarks"></a>Примечания

Эти константы определяют атрибуты текущего файла или каталога, заданного с помощью функции.

Атрибуты представлены следующими константами манифеста.

|Константа|Описание|
|-|-|
|`_A_ARCH`| Архив. Устанавливается при любом изменении файла и очищается командой BACKUP. Значение: 0x20|
|`_A_HIDDEN`| Скрытый файл. Такой файл не отображается командой DIR, если не указан параметр /AH. Возвращает сведения об обычных файлах и файлах, имеющих этот атрибут. Значение: 0x02|
|`_A_NORMAL`| Нормальный. Такой файл можно читать или изменять без ограничений. Значение: 0x00|
|`_A_RDONLY`| Только для чтения. Такой файл невозможно открыть для записи и невозможно создать файл с таким же именем. Значение: 0x01|
|`_A_SUBDIR`| Подкаталог. Значение: 0x10|
|`_A_SYSTEM`| Системный файл. Такой файл не отображается командой DIR, если не указан параметр /AS. Значение: 0x04|

Вы можете объединить несколько констант с помощью оператора OR (&#124;).

## <a name="see-also"></a>См. также

[Функции поиска имени файла](../c-runtime-library/filename-search-functions.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)
