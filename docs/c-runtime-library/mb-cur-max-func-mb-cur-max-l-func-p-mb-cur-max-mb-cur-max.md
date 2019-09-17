---
title: ___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max
ms.date: 11/04/2016
api_name:
- ___mb_cur_max_l_func
- __p___mb_cur_max
- ___mb_cur_max_func
- __mb_cur_max
api_location:
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- api-ms-win-crt-locale-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
- __mb_cur_max
helpviewer_keywords:
- __mb_cur_max
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
ms.assetid: 60d36108-1ca7-45a6-8ce7-68a91f13e3a1
ms.openlocfilehash: a37ae2134d92310d6a530c759559b5e4b4af00f6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944197"
---
# <a name="___mb_cur_max_func-___mb_cur_max_l_func-__p___mb_cur_max-__mb_cur_max"></a>___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max

Внутренняя функция CRT. Получает максимальное число байт в многобайтовом символе для текущего или указанного языкового стандарта.

## <a name="syntax"></a>Синтаксис

```cpp
int ___mb_cur_max_func(void);
int ___mb_cur_max_l_func(_locale_t locale);
int * __p___mb_cur_max(void);
#define __mb_cur_max (___mb_cur_max_func())
```

#### <a name="parameters"></a>Параметры

locale — структура языкового стандарта, из которой предполагается получать результаты. Если значение этого параметра — NULL, используется языковой стандарт текущего потока.

## <a name="return-value"></a>Возвращаемое значение

Максимальное число байт в многобайтовом символе для текущего языкового стандарта потока или указанного языкового стандарта.

## <a name="remarks"></a>Примечания

Это внутренняя функция, которую CRT использует для получения текущего значения макроса [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md) из локального хранилища потока. Рекомендуется использовать макрос `MB_CUR_MAX` для обеспечения переносимости кода.

Макрос `__mb_cur_max` — это удобный способ вызова функции `___mb_cur_max_func()`. Функция `__p___mb_cur_max` определяется для совместимости с Visual C++ 5.0 и более ранних версий.

Внутренние функции CRT связаны с конкретной реализацией и подлежат изменению в каждом выпуске. Мы не рекомендуем использовать их в коде.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`___mb_cur_max_func`, `___mb_cur_max_l_func`, `__p___mb_cur_max`|\<ctype.h>, \<stdlib.h>|

## <a name="see-also"></a>См. также

[MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)
