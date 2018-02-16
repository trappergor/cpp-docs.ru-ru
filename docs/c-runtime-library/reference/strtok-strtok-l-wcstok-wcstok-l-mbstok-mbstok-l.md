---
title: "Функции strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstok
- strtok
- _tcstok
- wcstok
dev_langs:
- C++
helpviewer_keywords:
- mbstok_l function
- strings [C++], searching
- tcstok function
- _tcstok function
- _strtok_l function
- strtok function
- mbstok function
- wcstok_l function
- _mbstok function
- tcstok_l function
- tokens, finding in strings
- _mbstok_l function
- wcstok function
- _wcstok_l function
- _tcstok_l function
- strtok_l function
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c56b69d9b4a8dedede82207976f742d3768f65d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="strtok-strtokl-wcstok-wcstokl-mbstok-mbstokl"></a>strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l
Находят следующий токен в строке с использованием текущего или переданного языкового стандарта. Есть более безопасные версии этих функций. См. раздел [Функции strtok_s _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).  
  
> [!IMPORTANT]
>  Функции `_mbstok` и `_mbstok_l` не могут использоваться в приложениях, запускаемых в среде выполнения Windows. Дополнительные сведения см. в разделе [функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *strtok(  
   char *strToken,  
   const char *strDelimit   
);  
wchar_t *wcstok(  
   wchar_t *strToken,  
   const wchar_t *strDelimit   
);  
unsigned char *_mbstok(  
   unsigned char*strToken,  
   const unsigned char *strDelimit   
);  
unsigned char *_mbstok(  
   unsigned char*strToken,  
   const unsigned char *strDelimit,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `strToken`  
 Строка, содержащая токен или токены.  
  
 `strDelimit`  
 Набор символов-разделителей.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на следующий токен, найденный в `strToken`. Они возвращают `NULL`, если больше токенов не найдено. Каждый вызов изменяет строку `strToken`, заменяя символом `NULL` первый разделитель, находящийся после возвращенного токена.  
  
## <a name="remarks"></a>Примечания  
 Функция `strtok` находит следующий токен в `strToken`. Набор символов в параметре `strDelimit` указывает возможные разделители токенов, которые требуется найти в `strToken` во время текущего вызова. Функции `wcstok` и `_mbstok` являются версиями функции `strtok` для расширенных и многобайтовых символов. Аргументы и возвращаемое значение `wcstok` представляют собой двухбайтовые строки; аргументы и возвращаемое значение `_mbstok` представляют собой многобайтовые строки. В остальном эти три функции ведут себя идентично.  
  
> [!IMPORTANT]
>  Эти функции представляют потенциальную угрозу, связанную с проблемой переполнения буфера. Проблемы переполнения буфера — это распространенный метод атак на системы, который приводит к несанкционированному повышению уровня прав. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 При первом вызове функции `strtok` она пропускает ведущие разделители и возвращает указатель на первый токен в `strToken`, завершая токен нуль-символом. Из оставшейся части `strToken` можно выделить другие токены с помощью последовательных вызовов функции `strtok`. Каждый вызов `strtok` изменяет `strToken` , вставляя нуль-символ после `token` возвращенного этим вызовом. Чтобы прочитать следующий токен из `strToken`, вызовите функцию `strtok` со значением `NULL` аргумента `strToken`. Значение `NULL` аргумента `strToken` приводит к тому, что функция `strtok` ищет следующий токен в измененной строке `strToken`. Аргумент `strDelimit` в разных вызовах может принимать любое значение, позволяя изменять набор разделителей.  
  
 Выходное значение зависит от настройки категории `LC_CTYPE` языкового стандарта; дополнительные сведения см. в разделе [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Версии этих функций без суффикса `_l` используют текущий языковой стандарт для данного поведения, зависимого от языкового стандарта. Версии с суффиксом `_l` идентичны, однако они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).  
  
> [!NOTE]
>  Каждая функция использует статическую локальную в потоке переменную для разбора строки на токены. Поэтому эти функции могут вызвать одновременно несколько потоков без нежелательных последствий. Однако в пределах одного потока чередование вызовов одной из этих функций с большой степенью вероятности приводит к повреждению данных и получению неточных результатов. При синтаксическом анализе разных строк сначала завершите анализ одной строки, а затем начинайте анализ следующей. Кроме того, помните о потенциальной опасности, возникающей при вызове одной из этих функций из цикла, в котором также вызывается другая функция. Если другая функция использует одну из этих функций, произойдет чередование последовательностей вызовов, что приведет к повреждению данных.  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstok`|`strtok`|`_mbstok`|`wcstok`|  
|`_tcstok`|`_strtok_l`|`_mbstok_l`|`_wcstok_l`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strtok`|\<string.h>|  
|`wcstok`|\<string.h> или \<wchar.h>|  
|`_mbstok`, `_mbstok_l`|\<mbstring.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_strtok.c  
// compile with: /W3  
// In this program, a loop uses strtok  
// to print all the tokens (separated by commas  
// or blanks) in the string named "string".  
//  
#include <string.h>  
#include <stdio.h>  
  
char string[] = "A string\tof ,,tokens\nand some  more tokens";  
char seps[]   = " ,\t\n";  
char *token;  
  
int main( void )  
{  
   printf( "Tokens:\n" );  
  
   // Establish string and get the first token:  
   token = strtok( string, seps ); // C4996  
   // Note: strtok is deprecated; consider using strtok_s instead  
   while( token != NULL )  
   {  
      // While there are tokens in "string"  
      printf( " %s\n", token );  
  
      // Get next token:   
      token = strtok( NULL, seps ); // C4996  
   }  
}  
```  
  
```Output  
Tokens:  
 A  
 string  
 of  
 tokens  
 and  
 some  
 more  
 tokens  
```  
  
## <a name="see-also"></a>См. также  
 [Операции со строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, _mbscspn, _mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)