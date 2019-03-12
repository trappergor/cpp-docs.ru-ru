---
title: _local_unwind2
ms.date: 11/04/2016
apiname:
- _local_unwind2
apilocation:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- _local_unwind2
- local_unwind2
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
ms.openlocfilehash: c62763ecbdd2c05e8cd7b6733ec1df4254362527
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743994"
---
# <a name="localunwind2"></a>_local_unwind2

Внутренняя функция CRT. Выполняет все обработчики завершения, перечисленные в указанной таблице области.

## <a name="syntax"></a>Синтаксис

```
void _local_unwind2(
   PEXCEPTION_REGISTRATION xr,
   int stop
);
```

#### <a name="parameters"></a>Параметры

*xr*<br/>
[in] Запись регистрации, которая связана с одной таблицей области видимости.

*stop*<br/>
[in] Лексический уровень, который указывает, где должна остановиться функция `_local_unwind2`.

## <a name="remarks"></a>Примечания

Этот метод используется только средой выполнения. Не вызывайте метод в коде.

Когда этот метод выполняет обработчики завершения, он начинает выполнение на текущем лексическом уровне и проходит все лексические уровни, пока не достигнет уровня, указанного параметром `stop`. Он не выполняет обработчики завершения на уровне, указанном параметром `stop`.

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
