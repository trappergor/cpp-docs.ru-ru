---
title: Константы разрешений файлов
ms.date: 11/04/2016
f1_keywords:
- _S_IWRITE
- _S_IREAD
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
ms.openlocfilehash: 7b9d99f8b0fc7daf8f7dc58db999c7f885a3dc8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648608"
---
# <a name="file-permission-constants"></a>Константы разрешений файлов

## <a name="syntax"></a>Синтаксис

```

#include <sys/stat.h>

```

## <a name="remarks"></a>Примечания

Одна из этих констант обязательна при указании `_O_CREAT` (`_open`, `_sopen`).

Аргумент `pmode` определяет настройки разрешений файла следующим образом.

|Константа|Значение|
|--------------|-------------|
|`_S_IREAD`|Разрешено чтение|
|`_S_IWRITE`|Разрешена запись|
|`_S_IREAD` &#124; `_S_IWRITE`|Разрешены чтение и запись|

При использовании в качестве аргумента `pmode` для функции `_umask` эта константа манифеста задает настройки разрешений следующим образом.

|Константа|Значение|
|--------------|-------------|
|`_S_IREAD`|Запись запрещена (файл доступен только для чтения)|
|`_S_IWRITE`|Чтение запрещено (файл доступен только для записи)|
|`_S_IREAD` &#124; `_S_IWRITE`|Чтение и запись запрещены|

## <a name="see-also"></a>См. также

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_umask](../c-runtime-library/reference/umask.md)<br/>
[Стандартные типы](../c-runtime-library/standard-types.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)