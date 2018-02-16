---
title: "isblank, iswblank, _isblank_l, _iswblank_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
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
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
dev_langs:
- C++
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5c3dff4f409fe57c67e00afe24f10cbb69c6f83b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="isblank-iswblank-isblankl-iswblankl"></a>isblank, iswblank, _isblank_l, _iswblank_l
Определяет, представляет ли целое число пустой символ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int isblank(  
   int c   
);  
int iswblank(  
   wint_t c   
);  
int _isblank_l(  
   int c,  
   _locale_t locale  
);  
int _iswblank_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Проверяемое целое число.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих подпрограмм возвращает ненулевое значение, если `c` является конкретным представлением пробела, символа горизонтальной табуляции или одного из символов языкового набора, которые используются для разделения слов в строке текста. Функция `isblank` возвращает ненулевое значение, если `c` является символом пробела (0x20) или горизонтальной табуляции (0x09). Результат проверки условия для функций `isblank` зависит от настройки категории `LC_CTYPE` для языкового стандарта. Дополнительные сведения см. в разделе [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Версии этих функций без суффикса `_l` используют текущий языковой стандарт для любого поведения, зависящего от языкового стандарта. Версии с суффиксом `_l` идентичны версиям без него, за исключением того, что они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
 Функция `iswblank` возвращает ненулевое значение, если `c` представляет собой расширенный символ, соответствующий стандартному пробелу или символу горизонтальной табуляции.  
  
 Поведение функций `isblank` и `_isblank_l` не определено, если `c` не является концом файла или не находится в диапазоне от 0 по 0xFF включительно. Если используется библиотека отладки CRT и `c` не является одним из этих значений, функции вызывают утверждение.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istblank`|`isblank`|[_ismbcblank](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswblank`|  
|`_istblank_l`|`_isblank_l`|[_ismbcblank_l](../../c-runtime-library/reference/ismbcgraph-functions.md)|`_iswblank_l`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`isblank`|\<ctype.h>|  
|`iswblank`|\<ctype.h> или \<wchar.h>|  
|`_isblank_l`|\<ctype.h>|  
|`_iswblank_l`|\<ctype.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)