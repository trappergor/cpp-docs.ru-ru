---
title: "_ismbblead, _ismbblead_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbblead_l
- _ismbblead
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
- ismbblead_l
- istlead
- _ismbblead
- _ismbblead_l
- ismbblead
- _istlead
dev_langs:
- C++
helpviewer_keywords:
- _ismbblead_l function
- ismbblead function
- _ismbblead function
- istlead function
- ismbblead_l function
- _istlead function
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 08d76a2e7fb30ffcef7e8fb8b96b5bf42a1454c6
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="ismbblead-ismbbleadl"></a>_ismbblead, _ismbblead_l
Проверяет символ, чтобы определить, является ли он старшим байтом многобайтового символа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _ismbblead(  
   unsigned int c   
);  
int _ismbblead_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Целое число, которое требуется проверить.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение, если целочисленное значение `c` является первым байтом многобайтового символа.  
  
## <a name="remarks"></a>Примечания  
 Многобайтовые символы состоят из старшего байта, за которым следует конечный байт. Старшие байты относятся к определенному диапазону данной кодировки. Например в кодовой странице 932 только старшие байты диапазону от 0x81-0x9F и от 0xE0 - 0xFC.  
  
 Функция`_ismbblead` использует текущий языковой стандарт для поведения, зависящего от языкового стандарта. Функция`_ismbblead_l` идентична за исключением того, что использует переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_istlead`|Всегда возвращает значение false|`_ismbblead`|Всегда возвращает значение false|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_ismbblead`|\<mbctype.h> или \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|  
|`_ismbblead_l`|\<mbctype.h> или \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|  
  
 \* Для констант манифестов, используемых в условиях проверки.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Классификация байтов](../../c-runtime-library/byte-classification.md)   
 [Подпрограммы _ismbb](../../c-runtime-library/ismbb-routines.md)
