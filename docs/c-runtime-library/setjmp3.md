---
title: _setjmp3
ms.date: 11/04/2016
apiname:
- _setjmp3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- setjmp3
- _setjmp3
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
ms.openlocfilehash: 4509738f8e0128e2f9277e744a5965f557f65439
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564015"
---
# <a name="setjmp3"></a>_setjmp3

Внутренняя функция CRT. Новая реализация функции `setjmp`.

## <a name="syntax"></a>Синтаксис

```
int _setjmp3(
   OUT jmp_buf env,
   int count,
   (optional parameters)
);
```

#### <a name="parameters"></a>Параметры

*env*<br/>
[out] Адрес буфера для хранения сведений о состоянии.

*count*<br/>
[in] Количество дополнительных объектов `DWORD`, хранимых в `optional parameters`.

*необязательные параметры*<br/>
[in] Дополнительные данные, отправленные встроенной функцией `setjmp`. Первое `DWORD` — это указатель функции, которая используется для очистки лишних данных и возврата к состоянию неизменяемого регистра. Второе `DWORD` — уровень повторной попытки, который необходимо восстановить. Все дальнейшие данные сохраняются в массиве универсальных данных в `jmp_buf`.

## <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 0.

## <a name="remarks"></a>Примечания

Не используйте эту функцию в программе C++. Это встроенная функция, не поддерживающая C++. Дополнительные сведения об использовании `setjmp` см. в статье [Using setjmp/longjmp](../cpp/using-setjmp-longjmp.md) (Использование setjmp и longjmp).

## <a name="requirements"></a>Требования

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[setjmp](../c-runtime-library/reference/setjmp.md)