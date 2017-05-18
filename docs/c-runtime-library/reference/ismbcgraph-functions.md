---
title: "_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbcpunct_l
- _ismbcblank
- _ismbcprint
- _ismbcgraph_l
- _ismbcblank_l
- _ismbcpunct
- _ismbcprint_l
- _ismbcspace_l
- _ismbcspace
- _ismbcgraph
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
- _ismbcspace
- _ismbcgraph
- _ismbcpunct
- ismbcspace_l
- ismbcgraph
- _ismbcgraph_l
- _ismbcprint
- _ismbcspace_l
- ismbcprint
- ismbcgraph_l
- ismbcspace
- ismbcpunct
dev_langs:
- C++
helpviewer_keywords:
- ismbcspace_l function
- _ismbcprint_l function
- ismbcspace function
- ismbcpunct function
- _ismbcspace_l function
- _ismbcprint function
- ismbcprint function
- _ismbcgraph function
- ismbcgraph_l function
- _ismbcpunct_l function
- ismbcpunct_l function
- ismbcprint_l function
- _ismbcpunct function
- ismbcgraph function
- _ismbcgraph_l function
- _ismbcspace function
ms.assetid: 8e0a5f47-ba64-4411-92a3-3c525d16e3be
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 602b5d1f3cd490213f3f849200eb155456627694
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="ismbcgraph-ismbcgraphl-ismbcprint-ismbcprintl-ismbcpunct-ismbcpunctl-ismbcblank-ismbcblankl-ismbcspace-ismbcspacel"></a>_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l
Определяет, является ли символ графическим, отображаемым символом, знаком препинания или пробелом.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _ismbcgraph(  
   unsigned int c   
);  
int _ismbcgraph_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcprint(  
   unsigned int c   
);  
int _ismbcprint_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcpunct(  
   unsigned int c  
);  
int _ismbcpunct_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcblank(  
   unsigned int c   
);  
int _ismbcblank_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcspace(  
   unsigned int c   
);  
int _ismbcspace_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Символ, который требуется определить.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих подпрограмм возвращает ненулевое значение, если символ удовлетворяет условию теста, или 0, если не удовлетворяет. Если `c` <= 255 и есть соответствующая подпрограмма `_ismbb` (например, `_ismbcalnum` соответствует `_ismbbalnum`), то результат равен возвращаемому значению соответствующей подпрограммы `_ismbb`.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что для поведения, зависящего от языкового стандарта, они используют переданный параметр языкового стандарта вместо текущего языкового стандарта. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций проверяет определенный многобайтовый символ на соответствие заданному условию.  
  
|Подпрограмма|Условие теста|Пример кодовой страницы 932|  
|-------------|--------------------|---------------------------|  
|`_ismbcgraph`|Графические символы|Возвращает ненулевое значение только в том случае, если `c` является однобайтовым представлением любого печатного символа ASCII или катаканы, кроме пробела ( ).|  
|`_ismbcprint`|Печатные символы|Возвращает ненулевое значение только в том случае, если `c` является однобайтовым представлением любого печатного символа ASCII или катаканы, включая пробел ( ).|  
|`_ismbcpunct`|Пунктуация|Возвращает ненулевое значение только в том случае, если `c` является однобайтовым представлением любого знака препинания ASCII или катаканы.|  
|`_ismbcblank`|Пробелы или символы горизонтальной табуляции|Возвращает ненулевое значение только в том случае, если `c` является символом пробела или горизонтальной табуляции: `c`=0x20 или `c`=0x09 соответственно.|  
|`_ismbcspace`|Пробел|Возвращает ненулевое значение только в том случае, если `c` является символом пробела: `c`=0x20 или 0x09<=`c`<=0x0D.|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_ismbcgraph`|\<mbstring.h>|  
|`_ismbcgraph_l`|\<mbstring.h>|  
|`_ismbcprint`|\<mbstring.h>|  
|`_ismbcprint_l`|\<mbstring.h>|  
|`_ismbcpunct`|\<mbstring.h>|  
|`_ismbcpunct_l`|\<mbstring.h>|  
|`_ismbcblank`|\<mbstring.h>|  
|`_ismbcblank_l`|\<mbstring.h>|  
|`_ismbcspace`|\<mbstring.h>|  
|`_ismbcspace_l`|\<mbstring.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Подпрограммы _ismbc](../../c-runtime-library/ismbc-routines.md)   
 [Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)   
 [Подпрограммы _ismbb](../../c-runtime-library/ismbb-routines.md)
