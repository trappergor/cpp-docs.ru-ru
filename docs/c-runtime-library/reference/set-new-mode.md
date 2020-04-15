---
title: _set_new_mode
ms.date: 4/2/2020
api_name:
- _set_new_mode
- _o__set_new_mode
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_new_mode
- _set_new_mode
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
ms.openlocfilehash: 3a27717d65714de54f477e4e2b3f243c4631fd8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332322"
---
# <a name="_set_new_mode"></a>_set_new_mode

Устанавливает новый режим обработчика для **malloc**.

## <a name="syntax"></a>Синтаксис

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>Параметры

*newhandlermode*<br/>
Новый режим обработчика для **malloc**; допустимое значение 0 или 1.

## <a name="return-value"></a>Возвращаемое значение

Возвращает предыдущий режим обработчика, установленный для **malloc.** Значение возврата 1 указывает на то, что при невыделении памяти **мэллок** ранее назывался новой рутиной обработчика; значение возврата 0 указывает на то, что это не так. Если аргумент *newhandlermode* не равен 0 или 1, возвращается -1.

## <a name="remarks"></a>Remarks

Функция **_set_new_mode** C++ задает новый режим обработчика для [malloc](malloc.md). Новый режим обработчика указывает, является ли, при сбое, **malloc** является вызов новой рутины обработчика, как установить [_set_new_handler.](set-new-handler.md) По умолчанию **malloc** не вызывает новую рутину обработчика при неспособности выделить память. Вы можете переопределить это поведение по умолчанию, так что, когда **malloc** не выделяет память, **malloc** вызывает новую рутину обработчика так же, как **новый** оператор делает, когда он не по той же причине. Дополнительные сведения см. в разделе об операторах [new](../../cpp/new-operator-cpp.md) и [delete](../../cpp/delete-operator-cpp.md)*справочника по языку C++*. Чтобы переопределить значение по умолчанию, вызовите:

```cpp
_set_new_mode(1);
```

в начале вашей программы или ссылки с Newmode.obj (см. [Варианты ссылки](../../c-runtime-library/link-options.md)).

Эта функция проверяет свои параметры. Если *newhandlermode* является чем-то иным, чем 0 или 1, функция вызывает недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, <strong>_set_new_mode</strong> возвращает -1 `EINVAL`и устанавливает **errno** к .

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_new_mode**|\<new.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Распределение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[Бесплатный](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
