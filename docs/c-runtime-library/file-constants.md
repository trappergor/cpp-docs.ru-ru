---
title: Константы файлов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _O_EXCL
- _O_RDWR
- _O_APPEND
- _O_RDONLY
- _O_TRUNC
- _O_CREAT
- _O_WRONLY
dev_langs:
- C++
helpviewer_keywords:
- _O_RDWR constant
- O_EXCL constant
- O_RDWR constant
- O_WRONLY constant
- O_APPEND constant
- O_CREAT constant
- _O_CREAT constant
- _O_APPEND constant
- _O_EXCL constant
- O_TRUNC constant
- _O_RDONLY constant
- _O_TRUNC constant
- O_RDONLY constant
- _O_WRONLY constant
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e026de7b18d6809251e49f71d382c741f62be512
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028977"
---
# <a name="file-constants"></a>Константы файлов

## <a name="syntax"></a>Синтаксис

```

#include <fcntl.h>

```

## <a name="remarks"></a>Примечания

Целочисленное выражение, образуемое из одной или нескольких этих констант, определяет тип разрешенных операций чтения или записи. Выражение образуется путем объединения одной или нескольких констант с константой режима преобразования.

Константы файла выглядят следующим образом:

|Константа|Описание:|
|-|-|
| `_O_APPEND`  | Перемещает файловый указатель в конец файла перед каждой операцией записи.  |
| `_O_CREAT`  | Создает новый файл и открывает его для записи. Игнорируется, если уже существует файл, заданный параметром *filename*.  |
| `_O_EXCL`  | Возвращает значение ошибки, если уже существует файл, заданный параметром *filename*. Применяется только при использовании в сочетании с `_O_CREAT`.  |
| `_O_RDONLY`  | Открывает только для чтения; если задан этот флаг, нельзя задать `_O_RDWR`, ни `_O_WRONLY`.  |
| `_O_RDWR`  | Открывает файл как для чтения, так и для записи; если задан этот флаг, нельзя задать `_O_RDONLY`, ни `_O_WRONLY`.  |
| `_O_TRUNC`  | Открывает и усекает до нулевой длины существующий файл; файл должен иметь разрешение на запись. Содержимое файла уничтожается. Если задан этот флаг, задать `_O_RDONLY` нельзя.  |
| `_O_WRONLY`  | Открывает файл только для записи; если задан этот флаг, нельзя задать `_O_RDONLY`, ни `_O_RDWR`.  |

## <a name="see-also"></a>См. также

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)