---
title: "strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
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
- strxfrm
- _tcsxfrm
- wcsxfrm
dev_langs:
- C++
helpviewer_keywords:
- strxfrm_l function
- _tcsxfrm function
- _strxfrm_l function
- strxfrm function
- wcsxfrm_l function
- wcsxfrm function
- string comparison [C++], transforming strings
- tcsxfrm function
- strings [C++], comparing locale
- _wcsxfrm_l function
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: b05ec00ae2144670844cd54de0900aa1412128ff
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="strxfrm-wcsxfrm-strxfrml-wcsxfrml"></a>strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l
Преобразует строку на основе данных языкового стандарта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t strxfrm(  
   char *strDest,  
   const char *strSource,  
   size_t count   
);  
size_t wcsxfrm(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count   
);  
size_t _strxfrm_l(  
   char *strDest,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
size_t wcsxfrm_l(  
   wchar_t *strDest,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `strDest`  
 Конечная строка.  
  
 `strSource`  
 Исходная строка.  
  
 `count`  
 Максимальное количество символов для размещения в `strDest`.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину преобразованной строки, не считая завершающий нуль-символ. Если возвращаемое значение больше либо равно `count`, содержимое `strDest` непредсказуемо. При возникновении ошибки каждая функция устанавливает значение параметра `errno` и возвращает `INT_MAX`. В случае недопустимого символа параметр `errno` получает значение `EILSEQ`.  
  
## <a name="remarks"></a>Примечания  
 Функция `strxfrm` преобразует строку, на которую указывает `strSource`, в новую упорядоченную форму, которая сохраняется в `strDest`. Преобразуется и размещается в конечной строке не более `count` символов, включая завершающий нуль-символ. Преобразование осуществляется с использованием параметра категории `LC_COLLATE` языкового стандарта. Дополнительные сведения по `LC_COLLATE` см. в разделе [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Функция `strxfrm` использует текущий языковой стандарт для поведения, зависящего от языкового стандарта; функция `_strxfrm_l` идентична предыдущей функции, но вместо текущего языкового стандарта в ней используется языковой стандарт, передаваемый в качестве параметра. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 После преобразования вызов функции `strcmp` с двумя преобразованными строками дает результаты, которые идентичны результату вызова функции `strcoll` применительно к двум исходным строкам. Как и функции `strcoll` и `stricoll`, функция `strxfrm` при необходимости автоматически обрабатывает строки многобайтовых символов.  
  
 `wcsxfrm` — это версия функции `strxfrm` для расширенных символов; строковые аргументы функции `wcsxfrm` представляют собой указатели на расширенные символы. В случае функции `wcsxfrm` после преобразования строк вызов функции `wcscmp` с двумя преобразованными строками дает результаты, которые идентичны результату вызова функции `wcscoll` применительно к двум исходным строкам. Поведение `wcsxfrm` и `strxfrm` идентично в противном случае. Функция `wcsxfrm` использует текущий языковой стандарт для поведения, зависящего от языкового стандарта; функция `_wcsxfrm_l` вместо текущего языкового стандарта использует языковой стандарт, который передается в качестве параметра.  
  
 Эти функции проверяют свои параметры. Если `strSource` — пустой указатель, или если `strDest` — пустой указатель (если count не равно нулю), или если `count` больше `INT_MAX`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `INT_MAX`.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsxfrm`|`strxfrm`|`strxfrm`|`wcsxfrm`|  
|`_tcsxfrm_l`|`_strxfrm_l`|`_strxfrm_l`|`_wcsxfrm_l`|  
  
 В языковом стандарте "C" порядок символов в наборе символов (кодировка ASCII) совпадает с лексикографическим порядком символов. Однако в других языковых стандартах порядок символов в наборе символов может отличаться от лексикографического порядка. Например, в некоторых европейских языковых стандартах символ a (значение 0x61) предшествует символу &\#x00E4; (значение 0xE4) в наборе символов, но ä предшествует символу a лексикографически.  
  
 При использовании языковых стандартов, в которых порядок символов в наборе символов и лексикографический порядок различаются, используйте функцию `strxfrm` для исходных строк, затем функцию `strcmp` на результирующих строках для лексикографического сравнения строк согласно категории `LC_COLLATE` текущего языкового стандарта. Таким образом, чтобы лексикографически сравнить две строки в приведенном ранее языковом стандарте, используйте функцию `strxfrm` для исходных строк, затем функцию `strcmp` для результирующих строк. Можно также использовать функцию `strcoll` вместо функции `strcmp` для исходных строк.  
  
 Функция `strxfrm` представляет собой оболочку [LCMapString](http://msdn.microsoft.com/library/windows/desktop/dd318700) с `LCMAP_SORTKEY`.  
  
 Значение следующего выражения — это размер массива, необходимого для хранения `strxfrm`-преобразования исходной строки:  
  
```  
1 + strxfrm( NULL, string, 0 )  
```  
  
 Только в языковом стандарте "C" функция `strxfrm` эквивалентна следующему:  
  
```  
strncpy( _string1, _string2, _count );  
return( strlen( _string1 ) );  
```  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strxfrm`|\<string.h>|  
|`wcsxfrm`|\<string.h> или \<wchar.h>|  
|`_strxfrm_l`|\<string.h>|  
|`_wcsxfrm_l`|\<string.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Операции со строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)
