---
title: ___setlc_active_func, ___unguarded_readlc_active_add_func
ms.date: 11/04/2016
apiname:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
ms.openlocfilehash: 244bb5b0bd6a15dab2de1ad2d6b71c2ae2f850bb
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743974"
---
# <a name="setlcactivefunc-unguardedreadlcactiveaddfunc"></a>___setlc_active_func, ___unguarded_readlc_active_add_func

УСТАРЕВШИЕ. Среда CRT экспортирует эти внутренние функции только для поддержания совместимости с двоичными данными.

## <a name="syntax"></a>Синтаксис

```cpp
int ___setlc_active_func(void);
int * ___unguarded_readlc_active_add_func(void);
```

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение не важно.

## <a name="remarks"></a>Примечания

Хотя внутренние функции CRT `___setlc_active_func` и `___unguarded_readlc_active_add_func` являются устаревшими и более не используются, они экспортируются библиотекой CRT для поддержания совместимости с двоичными данными. Изначальной целью функции `___setlc_active_func` был возврат числа текущих активных вызовов функции `setlocale`. Изначальной целью функции `___unguarded_readlc_active_add_func` был возврат числа функций, которые ссылаются на языковой стандарт, не блокируя его.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|Нет|

## <a name="see-also"></a>См. также

[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
