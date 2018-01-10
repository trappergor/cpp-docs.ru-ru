---
title: "iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- iscntrl
- _iswcntrl_l
- _iscntrl_l
- iswcntrl
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _istcntrl_l
- _iswcntrl_l
- iswcntrl
- _iscntrl_l
- iscntrl
- _istcntrl
dev_langs: C++
helpviewer_keywords:
- iscntrl function
- _iscntrl_l function
- _iswcntrl_l function
- _istcntrl function
- istcntrl function
- iswcntrl function
- _istcntrl_l function
ms.assetid: 616eebf9-aed4-49ba-ba2c-8677c8fe6fb5
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 35c0947d51b4caf239838a38a31df39226f7da50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="iscntrl-iswcntrl-iscntrll-iswcntrll"></a>iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l
Определяет, представляет ли целое число управляющий символ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int iscntrl(   
   int c   
);  
int iswcntrl(   
   wint_t c   
);  
int _iscntrl_l(   
   int c,  
   _locale_t locale  
);  
int _iswcntrl_l(   
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Проверяемое целое число  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих подпрограмм возвращает отличное от нуля значение, если `c` — конкретное представление управляющего символа. `iscntrl`возвращает ненулевое значение, если `c` управляющим символом (0x00 — 0x1F или 0x7F). Функция `iswcntrl` возвращает ненулевое значение, если `c` является расширенным управляющим символом. Каждая из этих подпрограмм возвращает 0, если `c` не удовлетворяет проверяемому условию.  
  
 Версии этих функций с суффиксом `_l` используют переданный параметр языкового стандарта вместо текущего языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
 Поведение функций `iscntrl` и `_iscntrl_l` не определено, если `c` не является концом файла или не находится в диапазоне от 0 по 0xFF включительно. Если используется библиотека отладки CRT и `c` не является одним из этих значений, функции вызывают утверждение.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istcntrl`|`iscntrl`|`iscntrl`|`iswcntrl`|  
|`_istcntrl_l`|`_iscntrl_l`|`_iscntrl_l`|`_iswcntrl_l`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`iscntrl`|\<ctype.h>|  
|`iswcntrl`|\<ctype.h> или \<wchar.h>|  
|`_iscntrl_l`|\<ctype.h>|  
|`_iswcntrl_l`|\<ctype.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)