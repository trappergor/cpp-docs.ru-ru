---
title: ___setlc_active_func, ___unguarded_readlc_active_add_func
ms.date: 11/04/2016
api_name:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
api_location:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
ms.openlocfilehash: a7dd7d74992aeddffead1c6ef0d52cbc69848dad
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957288"
---
# <a name="___setlc_active_func-___unguarded_readlc_active_add_func"></a>___setlc_active_func, ___unguarded_readlc_active_add_func

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
