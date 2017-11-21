---
title: "_mbsbtype, _mbsbtype_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsbtype_l
- _mbsbtype
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
- mbsbtype
- mbsbtype_l
- _mbsbtype_l
- _mbsbtype
dev_langs: C++
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a20ff8b10229714a434dc0f77748f37f9c15064a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="mbsbtype-mbsbtypel"></a>_mbsbtype, _mbsbtype_l
Возвращает тип байта в строке.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _mbsbtype(  
   const unsigned char *mbstr,  
   size_t count   
);  
int _mbsbtype_l(  
   const unsigned char *mbstr,  
   size_t count,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `mbstr`  
 Адрес последовательности многобайтовых символов.  
  
 `count`  
 Смещение в байтах относительно заголовка строки.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_mbsbtype`и `_mbsbtype_l` возвращает целочисленное значение, указывающее результат теста на указанный байт. Константы манифеста, представленные в приведенной ниже таблице, определены в файле Mbctype.h.  
  
|Возвращаемое значение|Тип байта|  
|------------------|---------------|  
|`_MBC_SINGLE` (0)|Однобайтовый символ. Например, в кодовой странице 932 `_mbsbtype` возвращает 0, если указанный байт — в диапазоне от 0x20 — 0x7E или 0xA1 - 0xDF.|  
|`_MBC_LEAD` (1)|Старший байт многобайтового символа. Например, в кодовой странице 932 `_mbsbtype` возвращает 1, если указанного байтового входит в диапазон 0x81-0x9F и от 0xE0 - 0xFC.|  
|`_MBC_TRAIL` (2)|Младший байт многобайтового символа. Например, в кодовой странице 932 `_mbsbtype` возвращает 2 в том случае, если указанного байтового диапазона 0x40-0x7E и 0x80 - 0xFC.|  
|`_MBC_ILLEGAL` (-1)|Строка `NULL`, недопустимый символ или байт `NULL` перед байтом со смещением `count` в `mbstr`.|  
  
## <a name="remarks"></a>Примечания  
 Функция `_mbsbtype` определяет тип байта в строке многобайтовых символов. Эта функция проверяет только байт со смещением `count` в `mbstr`, пропуская недопустимые символы перед указанным байтом.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Версия этой функции без суффикса `_l` использует текущий языковой стандарт для данной функциональности, зависящей от языкового стандарта; версия с суффиксом `_l` идентична версии без суффикса, но использует переданный параметр языкового стандарта. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 Если входная строка имеет значение `NULL`, вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL`, и функция возвращает значение `_MBC_ILLEGAL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_mbsbtype`|\<mbstring.h>|\<mbctype.h>*|  
|`_mbsbtype_l`|\<mbstring.h>|\<mbctype.h>*|  
  
 \* Для констант манифеста используются в качестве возвращаемых значений.  
  
 Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Классификация байтов](../../c-runtime-library/byte-classification.md)