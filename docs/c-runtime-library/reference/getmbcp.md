---
title: _getmbcp
ms.date: 4/2/2020
api_name:
- _getmbcp
- _o__getmbcp
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getmbcp
- getmbcp
helpviewer_keywords:
- code pages, determining current
- _getmbcp function
- getmbcp function
ms.assetid: 2db202d4-5c3d-4871-a0b8-ceb0b79ee7bb
ms.openlocfilehash: 9d1582f8763528eb344acd53d06a169a689140f4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344246"
---
# <a name="_getmbcp"></a>_getmbcp

Извлекает текущую кодовую страницу.

## <a name="syntax"></a>Синтаксис

```C
int _getmbcp( void );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает текущую многобайтовую кодовую страницу. Возвращаемое значение 0 означает, что используется однобайтовая кодовая страница.

## <a name="remarks"></a>Remarks

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_getmbcp**|\<mbctype.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[_setmbcp](setmbcp.md)<br/>
