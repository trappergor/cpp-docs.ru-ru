---
title: _except_handler3
ms.date: 11/04/2016
api_name:
- _except_handler3
api_location:
- msvcrt.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _except_handler3
- except_handler3
helpviewer_keywords:
- _except_handler3 function
- except_handler3 function
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
ms.openlocfilehash: 5e1dbab97e0f193d4ff59c19229d2c00e2cd7d6a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944481"
---
# <a name="_except_handler3"></a>_except_handler3

Внутренняя функция CRT. Используется платформой для поиска подходящего обработчика исключений для обработки текущего исключения.

## <a name="syntax"></a>Синтаксис

```
int _except_handler3(
   PEXCEPTION_RECORD exception_record,
   PEXCEPTION_REGISTRATION registration,
   PCONTEXT context,
   PEXCEPTION_REGISTRATION dispatcher
);
```

#### <a name="parameters"></a>Параметры

*exception_record*<br/>
[in] Сведения о конкретном исключении.

*registration*<br/>
[in] Запись, которая указывает, какую таблицу области видимости следует использовать для поиска обработчика исключений.

*context*<br/>
[in] Зарезервировано.

*dispatcher*<br/>
[in] Зарезервировано.

## <a name="return-value"></a>Возвращаемое значение

Если исключение должно быть отброшено, возвращает значение `DISPOSITION_DISMISS`. Если исключение должно быть передано на уровень вверх в инкапсулируемые обработчики исключений, возвращает значение `DISPOSITION_CONTINUE_SEARCH`.

## <a name="remarks"></a>Примечания

Если этот метод находит подходящий обработчик исключений, он передает исключение в обработчик. В этой ситуации метод не возвращается к вызвавшему его коду, и возвращаемое значение несущественно.

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
