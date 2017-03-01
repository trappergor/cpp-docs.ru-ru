---
title: "_get_current_locale | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_current_locale
apilocation:
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
apitype: DLLExport
f1_keywords:
- get_current_locale
- __get_current_locale
- _get_current_locale
dev_langs:
- C++
helpviewer_keywords:
- get_current_locale function
- _get_current_locale function
- locales, getting information on
- __get_current_locale function
ms.assetid: 572217f2-a37a-4105-a293-a250b4fabd99
caps.latest.revision: 13
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 9c03528f5c85e7ac0ce70202486c8ee92ffadad0
ms.lasthandoff: 02/24/2017

---
# <a name="getcurrentlocale"></a>_get_current_locale
Получает объект языкового стандарта, представляющий текущий языковой стандарт.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_locale_t _get_current_locale(void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект языкового стандарта, представляющий текущий языковой стандарт.  
  
## <a name="remarks"></a>Примечания  
 Функция `_get_current_locale` получает текущий языковой стандарт и возвращает представляющий его объект языкового стандарта.  
  
 Предыдущее название данной функции `__get_current_locale` (с&2; символами подчеркивания в начале) использовать не рекомендуется.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_get_current_locale`|\<locale.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Эквивалент отсутствует.  
  
## <a name="see-also"></a>См. также  
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../../c-runtime-library/reference/free-locale.md)
