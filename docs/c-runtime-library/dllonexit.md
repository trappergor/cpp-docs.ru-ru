---
title: __dllonexit
ms.date: 11/04/2016
api_name:
- __dllonexit
api_location:
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __dllonexit
helpviewer_keywords:
- __dllonexit
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
ms.openlocfilehash: 61d63c751dd755bf8a7680c674681e114945814b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940433"
---
# <a name="__dllonexit"></a>__dllonexit

Регистрирует подпрограмму, вызываемую во время выхода.

## <a name="syntax"></a>Синтаксис

```
_onexit_t __dllonexit(   _onexit_t func,
   _PVFV **  pbegin,
   _PVFV **  pend
   )
```

#### <a name="parameters"></a>Параметры

*func*<br/>
Указатель на функцию, которая должна выполняться при выходе.

*pbegin*<br/>
Указатель на переменную, указывающую на начало списка функций, которые должны выполняться при отключении.

*pend*<br/>
Указатель на переменную, указывающую на конец списка функций, которые должны выполняться при отключении.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращается указатель на функцию пользователя. В противном случае возвращается указатель **NULL**.

## <a name="remarks"></a>Примечания

Функция `__dllonexit` аналогична функции [_onexit](../c-runtime-library/reference/onexit-onexit-m.md) за тем исключением, что глобальные переменные, которые она использует, не видны подпрограмме. Вместо глобальных переменных в этой функции применяются параметры `pbegin` и `pend`.

Функции `_onexit` и `atexit` в библиотеке DLL, связанной с файлом MSVCRT.LIB, должны содержать собственный список atexit/_onexit. Эта подпрограмма представляет собой рабочий процесс, который вызывают такие библиотеки DLL.

Тип `_PVFV` определяется как `typedef void (__cdecl *_PVFV)(void)`.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный файл|
|-------------|-------------------|
|__dllonexit|onexit.c|

## <a name="see-also"></a>См. также

[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)
