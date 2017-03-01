---
title: "_ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbclegal_l
- _ismbclegal
- _ismbcsymbol
- _ismbcsymbol_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ismbcsymbol_l
- _ismbcsymbol_l
- _ismbcsymbol
- _ismbclegal_l
- _ismbclegal
- ismbclegal_l
- ismbcsymbol
- ismbclegal
dev_langs:
- C++
helpviewer_keywords:
- ismbcsymbol function
- ismbclegal_l function
- _istlegal_l function
- istlegal function
- _istlegal function
- _ismbcsymbol function
- _ismbclegal_l function
- ismbclegal function
- ismbcsymbol_l function
- _ismbclegal function
- _ismbcsymbol_l function
- istlegal_l function
ms.assetid: 31bf1ea5-b56f-4e28-b21e-b49a2cf93ffc
caps.latest.revision: 18
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
ms.openlocfilehash: 561e0e677200e075b94fce0e354691bcdbce1505
ms.lasthandoff: 02/24/2017

---
# <a name="ismbclegal-ismbclegall-ismbcsymbol-ismbcsymboll"></a>_ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l
Проверяет, является ли многобайтовый допустимым символьным знаком.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _ismbclegal(  
   unsigned int c   
);  
int _ismbclegal_l(  
   unsigned int c,   
   _locale_t locale  
);  
int _ismbcsymbol(  
   unsigned int c   
);  
int _ismbcsymbol_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Символ, который требуется проверить.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих процедур возвращает ненулевое значение, если символ удовлетворяет условию теста, или 0, если не удовлетворяет. Если `c`<= 255 и есть соответствующая подпрограмма `_ismbb` (например, `_ismbcalnum` соответствует `_ismbbalnum`), то результат равен возвращаемому значению соответствующей подпрограммы `_ismbb`.  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций проверяет определенный многобайтовый символ на соответствие заданному условию.  
  
 Версии этих функций с суффиксом `_l` идентичны, за исключением того, что для поведения, зависящего от языкового стандарта, они используют переданный параметр языкового стандарта вместо текущего языкового стандарта. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
|Подпрограмма|Условие теста|Пример кодовой страницы 932|  
|-------------|--------------------|---------------------------|  
|`_ismbclegal`|Допустимый многобайтовый символ|Возвращает ненулевое значение только в том случае, если первый байт `c` находится в диапазонах 0x81–0x9F или 0xE0–0xFC, а второй — в диапазонах 0x40–0x7E или 0x80–FC.|  
|`_ismbcsymbol`|Многобайтовый символ|Возвращает ненулевое значение только в том случае, если 0x8141<=`c`<=0x81AC.|  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_istlegal`|Всегда возвращает значение false|`_ismbclegal`|Всегда возвращает значение false.|  
|`_istlegal_l`|Всегда возвращает значение false|`_ismbclegal_l`|Всегда возвращает значение false.|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_ismbclegal,_ismbclegal_l`|\<mbstring.h>|  
|`_ismbcsymbol,_ismbcsymbol_l`|\<mbstring.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Подпрограммы _ismbc](../../c-runtime-library/ismbc-routines.md)   
 [Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)   
 [Подпрограммы _ismbb](../../c-runtime-library/ismbb-routines.md)
