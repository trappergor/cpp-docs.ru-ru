---
title: "_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_stricmp_l"
  - "_mbsicmp"
  - "_wcsicmp"
  - "_mbsicmp_l"
  - "_stricmp"
  - "_wcsicmp_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ftcsicmp"
  - "_stricmp"
  - "wcsicmp_l"
  - "_wcsicmp"
  - "_tcsicmp"
  - "_strcmpi"
  - "stricmp_l"
  - "_mbsicmp"
  - "_fstricmp"
  - "mbsicmp_l"
  - "mbsicmp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fstricmp - функция"
  - "_ftcsicmp - функция"
  - "_mbsicmp - функция"
  - "_mbsicmp_l - функция"
  - "_strcmpi - функция"
  - "_stricmp - функция"
  - "_stricmp_l - функция"
  - "_tcsicmp - функция"
  - "_wcsicmp - функция"
  - "_wcsicmp_l - функция"
  - "fstricmp - функция"
  - "ftcsicmp - функция"
  - "mbsicmp - функция"
  - "mbsicmp_l - функция"
  - "stricmp_l - функция"
  - "сравнение строк [C++], строчные буквы"
  - "строки [C++], сравнение"
  - "tcsicmp - функция"
  - "wcsicmp_l - функция"
ms.assetid: 0e1ee515-0d75-435a-a445-8875d4669b50
caps.latest.revision: 28
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет сравнение строк без учета регистра.  
  
> [!IMPORTANT]
>  Функции `_mbsicmp` и `_mbsicmp_l` не могут использоваться в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _stricmp(  
   const char *string1,  
   const char *string2   
);  
int _wcsicmp(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbsicmp(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _stricmp_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale  
);  
int _wcsicmp_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale  
);  
int _mbsicmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `string1, string2`  
 Строки с завершающим нулем для сравнения.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Возвращаемое значение отражает взаимосвязь `string1` со `string2`, как показано ниже.  
  
|Возвращаемое значение|Описание|  
|---------------------------|--------------|  
|\< 0|`string1` меньше `string2`|  
|0|`string1` идентично `string2`|  
|\> 0|`string1` больше `string2`|  
  
 При ошибке `_mbsicmp` возвращает `_NLSCMPERROR`, которая определена в \<string.h\> и \<mbstring.h\>.  
  
## Заметки  
 Функция `_stricmp` выполняет порядковое сравнение версий `string1` и `string2` в нижнем регистре и возвращает значение, показывающее их взаимосвязь.  `_stricmp` отличается от `_stricoll` тем, что на сравнение `_stricmp` влияет только тип `LC_CTYPE`, определяющий регистр символов.  Функция `_stricoll` сравнивает строки в соответствии с категориями `LC_CTYPE` и `LC_COLLATE` языкового стандарта, который включает как регистр, так и порядок сортировки.  Подробнее о категории `LC_COLLATE` см. в разделах [setlocale](../Topic/setlocale,%20_wsetlocale.md) и [Категории языкового стандарта](../../c-runtime-library/locale-categories.md).  Версии этих функций без суффикса `_l` используют текущий языковой стандарт во время операций, зависящих от языкового стандарта.  Версии с суффиксом идентичны за исключением того, что вместо этого они используют переданный языковой стандарт.  Если языковой стандарт не задан, используется языковой стандарт C.  Подробнее: [Языковой стандарт](../../c-runtime-library/locale.md).  
  
> [!NOTE]
>  `_stricmp` равно `_strcmpi`.  Они взаимозаменяемы, но предпочтительнее стандарт `_stricmp`.  
  
 Функция `_strcmpi` эквивалентна `_stricmp` и предоставляется только для обеспечения обратной совместимости.  
  
 Так как `_stricmp` производит сравнение в нижнем регистре, это может стать причиной непредвиденного поведения.  
  
 Для иллюстрации того, что преобразование `_stricmp` влияет на результат сравнения, возьмем две строки: JOHNSTON и JOHN\_HENRY.  Строка JOHN\_HENRY будет считаться меньше JOHNSTON, так как "\_" имеет меньшее значение ASCII, чем S в нижнем регистре.  В действительности любой символ, имеющий значение ASCII в диапазоне от 91 до 96, считается меньше любой буквы.  
  
 Если функция [strcmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md) используется вместо `_stricmp`, то JOHN\_HENRY будет больше JOHNSTON.  
  
 Функции `_wcsicmp` и `_mbsicmp` являются версиями функции `_stricmp` для расширенных и многобайтовых символов.  Аргументы и возвращаемое значение `_wcsicmp` представляют собой двухбайтовые строки; аргументы и возвращаемое значение `_mbsicmp` представляют собой многобайтовые строки.  `_mbsicmp` распознает последовательности многобайтовых символов в соответствии с текущей многобайтовой кодовой страницей и возвращает `_NLSCMPERROR` при ошибке.  Для получения дополнительной информации см. [Кодовые страницы](../../c-runtime-library/code-pages.md).  В остальном эти три функции ведут себя идентично.  
  
 `_wcsicmp` и `wcscmp` ведут себя идентично за исключением того, что `wcscmp` не выполняет преобразование аргументов в нижний регистр перед их сравнением.  `_mbsicmp` и `_mbscmp` ведут себя идентично за исключением того, что `_mbscmp` не выполняет преобразование аргументов в нижний регистр перед их сравнением.  
  
 Необходимо вызвать [setlocale](../Topic/setlocale,%20_wsetlocale.md) для того, чтобы функция `_wcsicmp` могла работать с символами Latin 1.  По умолчанию действует языковой стандарт C, таким образом, например, ä не будет считаться равным Ä.  Вызовите `setlocale` с любым языковым стандартом, отличным от C, перед вызовом `_wcsicmp`.  Следующий пример демонстрирует, насколько функция `_wcsicmp` чувствительна к языковому стандарту:  
  
```  
// crt_stricmp_locale.c  
#include <string.h>  
#include <stdio.h>  
#include <locale.h>  
  
int main() {  
   setlocale(LC_ALL,"C");   // in effect by default  
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare fails  
   setlocale(LC_ALL,"");  
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare succeeds  
}  
```  
  
 Альтернативой служит вызов [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md) и передача возвращаемого объекта языкового стандарта в качестве параметра в `_wcsicmp_l`.  
  
 Все эти функции проверяют свои параметры.  Если `string1` или `string2` — неопределенные указатели, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `_NLSCMPERROR` и устанавливают для `errno` значение `EINVAL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsicmp`|`_stricmp`|`_mbsicmp`|`_wcsicmp`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_stricmp`, `_stricmp_l`|\<string.h\>|  
|`_wcsicmp`, `_wcsicmp_l`|\<string.h\> или \<wchar.h\>|  
|`_mbsicmp`, `_mbsicmp_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_stricmp.c  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
  
   // Case sensitive  
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );  
   result = strcmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof(tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof(tmp), "equal to" );  
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );  
  
   // Case insensitive (could use equivalent _stricmp)  
   result = _stricmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof(tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof(tmp), "equal to" );  
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );  
}  
```  
  
  **Сравните строки:**  
 **The quick brown dog jumps over the lazy fox**  
 **The QUICK brown dog jumps over the lazy fox**  
 **strcmp:   String 1 is greater than string 2**  
 **\_stricmp:  String 1 is equal to string 2**   
## Эквивалент в .NET Framework  
 [System::String::Compare](https://msdn.microsoft.com/en-us/library/system.string.compare.aspx)  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [\_memicmp, \_memicmp\_l](../../c-runtime-library/reference/memicmp-memicmp-l.md)   
 [strcmp, wcscmp, \_mbscmp](../Topic/strcmp,%20wcscmp,%20_mbscmp.md)   
 [Функции strcoll](../../c-runtime-library/strcoll-functions.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)