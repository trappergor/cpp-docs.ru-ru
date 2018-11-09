---
title: _lock
ms.date: 11/04/2016
apiname:
- _lock
apilocation:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- lock
- _lock
helpviewer_keywords:
- lock function
- _lock function
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
ms.openlocfilehash: c2e57af90bb9b7c6a4ba0e9efdd1dc1dc0bdb985
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606899"
---
# <a name="lock"></a>_lock

Получает многопоточную блокировку.

> [!IMPORTANT]
>  Эта функция устарела. Начиная с Visual Studio 2015 она недоступна в CRT.

## <a name="syntax"></a>Синтаксис

```
void __cdecl _lock
   int locknum
);
```

#### <a name="parameters"></a>Параметры

*locknum*<br/>
[in] Идентификатор блокировки, которую нужно получить.

## <a name="remarks"></a>Примечания

Если блокировка уже была получена, этот метод все равно получает блокировку и вызывает внутреннюю ошибку среды выполнения языка C (CRT). Если метод не может получить блокировку, он завершается с неустранимой ошибкой и устанавливает код ошибки `_RT_LOCK`.

## <a name="requirements"></a>Требования

**Источник:** mlock.c

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[_unlock](../c-runtime-library/unlock.md)