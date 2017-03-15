---
title: ___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ___mb_cur_max_l_func
- __p___mb_cur_max
- ___mb_cur_max_func
- __mb_cur_max
apilocation:
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
- __mb_cur_max
dev_langs:
- C++
helpviewer_keywords:
- __mb_cur_max
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
ms.assetid: 60d36108-1ca7-45a6-8ce7-68a91f13e3a1
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 643635c679e873a8f9d5221bc67e52a8246e272f
ms.lasthandoff: 02/24/2017

---
# <a name="mbcurmaxfunc-mbcurmaxlfunc-pmbcurmax-mbcurmax"></a>___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max
Внутренняя функция CRT. Получает максимальное число байт в многобайтовом символе для текущего или указанного языкового стандарта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
int ___mb_cur_max_func(void);  
int ___mb_cur_max_l_func(_locale_t locale);  
int * __p___mb_cur_max(void);  
#define __mb_cur_max (___mb_cur_max_func())  
```  
  
#### <a name="parameters"></a>Параметры  
 языковой стандарт  
 Структура языкового стандарта, из которой предполагается получать результаты. Если значение этого параметра — NULL, используется языковой стандарт текущего потока.  
  
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
