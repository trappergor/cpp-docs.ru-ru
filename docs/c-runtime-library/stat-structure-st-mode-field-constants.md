---
title: Константы поля st_mode структуры _stat
ms.date: 11/04/2016
f1_keywords:
- S_IFCHR
- S_IFDIR
- _S_IWRITE
- S_IFMT
- _S_IFDIR
- _S_IREAD
- S_IEXEC
- _S_IEXEC
- _S_IFMT
- S_IWRITE
- S_IFREG
- S_IREAD
- _S_IFCHR
- _S_IFREG
helpviewer_keywords:
- S_IFDIR constant
- stat structure
- S_IWRITE constant
- S_IEXEC constant
- _S_IFREG constant
- S_IREAD constant
- stat structure, constants
- _S_IFMT constant
- st_mode field constants
- S_IFMT constant
- _S_IEXEC constant
- _S_IWRITE constant
- _S_IFDIR constant
- S_IFREG constant
- S_IFCHR constant
- _S_IREAD constant
- _S_IFCHR constant
ms.assetid: fd462004-7563-4766-8443-30b0a86174b6
ms.openlocfilehash: 88b81ac5450d04a5a3e617af4658bb6e73fb4dd9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502223"
---
# <a name="stat-structure-stmode-field-constants"></a>Константы поля st_mode структуры _stat

## <a name="syntax"></a>Синтаксис

```

#include <sys/stat.h>

```

## <a name="remarks"></a>Примечания

Эти константы помогают указать тип файла в поле **st_mode** структуры [_stat](../c-runtime-library/standard-types.md).

Ниже перечислены константы битовой маски.

|Константа|Значение|
|--------------|-------------|
|`_S_IFMT`|Маска типа файла|
|`_S_IFDIR`|Каталог|
|`_S_IFCHR`|Специальный символ (если задана, указывает устройство)|
|`_S_IFREG`|Регулярное|
|`_S_IREAD`|Разрешение на чтение, владелец|
|`_S_IWRITE`|Разрешение на запись, владелец|
|`_S_IEXEC`|Разрешение на выполнение или поиск, владелец|

## <a name="see-also"></a>См. также

[_stat, _wstat Functions](../c-runtime-library/reference/stat-functions.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[Стандартные типы](../c-runtime-library/standard-types.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)