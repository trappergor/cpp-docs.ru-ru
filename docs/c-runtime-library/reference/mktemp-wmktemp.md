---
title: "_mktemp, _wmktemp | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wmktemp
- _mktemp
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
dev_langs:
- C++
helpviewer_keywords:
- _wmktemp function
- _mktemp function
- files [C++], temporary
- tmktemp function
- _tmktemp function
- wmktemp function
- mktemp function
- temporary files [C++]
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
caps.latest.revision: 25
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
ms.openlocfilehash: b6b5f2f059084e1f5dd66d75b5f5af5f2ade2473
ms.lasthandoff: 02/24/2017

---
# <a name="mktemp-wmktemp"></a>_mktemp, _wmktemp
Создает уникальное имя файла. Существуют более безопасные версии этих функций; см. раздел [_mktemp_s, _wmktemp_s](../../c-runtime-library/reference/mktemp-s-wmktemp-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *_mktemp(  
   char *template   
);  
wchar_t *_wmktemp(  
   wchar_t *template   
);  
template <size_t size>  
char *_mktemp(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wmktemp(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 `template`  
 Шаблон имени файла.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает указатель на измененный шаблон. Функция возвращает `NULL`, если значение `template` неправильно сформировано или невозможно создать больше уникальных имен на основе данного шаблона.  
  
## <a name="remarks"></a>Примечания  
 Функция `_mktemp` создает уникальное имя файла, изменяя аргумент `template`. Функция `_mktemp` автоматически требуемым образом обрабатывает аргументы в виде многобайтовых строк, распознавая многобайтовые последовательности символов в соответствии с текущей многобайтовой кодовой страницей, используемой системой времени выполнения. `_wmktemp` — это версия с расширенными символами для `_mktemp`; аргумент и возвращаемое значение `_wmktemp` являются строками с расширенными символами. В остальных отношениях поведение функций `_wmktemp` и `_mktemp` идентично, за исключением того, что функция `_wmktemp` не обрабатывает многобайтовые строки.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmktemp`|`_mktemp`|`_mktemp`|`_wmktemp`|  
  
 Аргумент `template` имеет форму `base`XXXXXX, где `base` является частью нового имени файла, который вы указали, а X — это заполнитель для символа, указанного в `_mktemp`. Каждый символ заполнителя в функции `template` должен быть обозначен символом X в верхнем регистре. Функция `_mktemp` сохраняет `base` и заменяет первый конечный символ X на букву. Функция `_mktemp` заменяет следующие конечные символы X пятизначным числом; это значение является уникальным номером, определяющим вызывающий процесс, а в многопоточных программах — вызывающий поток.  
  
 Каждый успешный вызов функции `_mktemp` изменяет `template`. В каждом последующем вызове из того же процесса или потока с таким же аргументом `template` функция `_mktemp` проверяет имена файлов, совпадающих с именами, которые были возвращены `_mktemp` в предыдущих вызовах. Если файл не существует для указанного имени, функция `_mktemp` возвращает это имя. Если файлы существуют для всех ранее возвращенных имен, функция `_mktemp` создает новое имя, заменяя букву, которая использовалась в ранее возвращенном имени, следующей доступной строчной буквой по порядку от "a" до "z". Например, если `base` — это  
  
```  
fn  
```  
  
 а пятизначное число, предоставляемое `_mktemp`, — 12345, то возвращается имя:  
  
```  
fna12345  
```  
  
 Если это имя используется для создания файла FNA12345 и этот файл существует, то следующее имя, возвращаемое из того же процесса или потока с таким же аргументом `base` для `template` будет  
  
```  
fnb12345  
```  
  
 Если файл FNA12345 не существует, то опять возвращается следующее имя:  
  
```  
fna12345  
```  
  
 Функция `_mktemp` может создать до 26 уникальных имен файлов для любого заданного сочетания значений базы и шаблона. Таким образом, FNZ12345 является последним уникальным именем файла, которое может создать функция `_mktemp` для значений `base` и `template`, используемых в этом примере.  
  
 В случае сбоя задается значение `errno`. Если `template` имеет недопустимый формат (например, менее 6 символов X), то для `errno` задается значение `EINVAL`. Если функции `_mktemp` не удается создать уникальное имя, так как все 26 возможных имен уже существуют, то `_mktemp` задает для шаблона пустую строку и возвращает `EEXIST`.  
  
 В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_mktemp`|\<io.h>|  
|`_wmktemp`|\<io.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_mktemp.c  
// compile with: /W3  
/* The program uses _mktemp to create  
 * unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
#include <errno.h>  
  
char *template = "fnXXXXXX";  
char *result;  
char names[27][9];  
  
int main( void )  
{  
   int i;  
   FILE *fp;  
  
   for( i = 0; i < 27; i++ )  
   {  
      strcpy_s( names[i], sizeof( names[i] ), template );  
      /* Attempt to find a unique filename: */  
      result = _mktemp( names[i] );  // C4996  
      // Note: _mktemp is deprecated; consider using _mktemp_s instead  
      if( result == NULL )  
      {  
         printf( "Problem creating the template\n" );  
         if (errno == EINVAL)  
         {  
             printf( "Bad parameter\n");  
         }  
         else if (errno == EEXIST)  
         {  
             printf( "Out of unique filenames\n");   
         }  
      }  
      else  
      {  
         fopen_s( &fp, result, "w" );  
         if( fp != NULL )  
            printf( "Unique filename is %s\n", result );  
         else  
            printf( "Cannot open %s\n", result );  
         fclose( fp );  
      }  
   }  
}  
```  
  
```Output  
Unique filename is fna03912  
Unique filename is fnb03912  
Unique filename is fnc03912  
Unique filename is fnd03912  
Unique filename is fne03912  
Unique filename is fnf03912  
Unique filename is fng03912  
Unique filename is fnh03912  
Unique filename is fni03912  
Unique filename is fnj03912  
Unique filename is fnk03912  
Unique filename is fnl03912  
Unique filename is fnm03912  
Unique filename is fnn03912  
Unique filename is fno03912  
Unique filename is fnp03912  
Unique filename is fnq03912  
Unique filename is fnr03912  
Unique filename is fns03912  
Unique filename is fnt03912  
Unique filename is fnu03912  
Unique filename is fnv03912  
Unique filename is fnw03912  
Unique filename is fnx03912  
Unique filename is fny03912  
Unique filename is fnz03912  
Problem creating the template.  
Out of unique filenames.  
```  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_getpid](../../c-runtime-library/reference/getpid.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)
