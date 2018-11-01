---
title: _set_new_mode
ms.date: 11/04/2016
apiname:
- _set_new_mode
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_new_mode
- _set_new_mode
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
ms.openlocfilehash: 0228170e4ab5b55b4b061fa61a412766de77a063
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602466"
---
# <a name="setnewmode"></a>_set_new_mode

Задает новый режим обработчика для **malloc**.

## <a name="syntax"></a>Синтаксис

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>Параметры

*newhandlermode*<br/>
Новый режим обработчика для **malloc**; допустимое значение — 0 или 1.

## <a name="return-value"></a>Возвращаемое значение

Возвращает предыдущий обработчик режима для **malloc**. Возвращаемое значение 1 указывает, что в случае сбоя процесса выделения памяти, **malloc** прежнее название — новую подпрограмму обработчика; возвращаемое значение 0 указывает, что этого не произошло. Если *newhandlermode* аргумент не равен 0 или 1, возвращается значение -1.

## <a name="remarks"></a>Примечания

Функция **_set_new_mode** C++ задает новый режим обработчика для [malloc](malloc.md). Новый режим обработки указывает, что в случае сбоя **malloc** должен вызывать новую подпрограмму обработчика, заданную функцией [_set_new_handler](set-new-handler.md). По умолчанию **malloc** не вызывает новую подпрограмму обработчика в случае сбоя процесса выделения памяти. Можно переопределить это поведение по умолчанию, чтобы, когда **malloc** не удается выделить память, **malloc** вызывала новую подпрограмму обработчика таким же образом, как **новый** делает оператор При сбое по той же причине. Дополнительные сведения см. в разделе об операторах [new](../../cpp/new-operator-cpp.md) и [delete](../../cpp/delete-operator-cpp.md) *справочника по языку C++*. Чтобы переопределить значение по умолчанию, вызовите:

```cpp
_set_new_mode(1);
```

на ранних этапах программы или выполните компоновку с использованием Newmode.obj (см. раздел [Параметры ссылок](../../c-runtime-library/link-options.md)).

Эта функция проверяет свои параметры. Если *newhandlermode* ничего от 0 или 1, функция вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, <strong>_set_new_mode</strong> возвращает -1 и задает **errno** для `EINVAL`.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_new_mode**|\<new.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
