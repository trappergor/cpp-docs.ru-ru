---
title: "_mktemp_s, _wmktemp_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mktemp_s
- _wmktemp_s
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
apitype: DLLExport
f1_keywords:
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
dev_langs:
- C++
helpviewer_keywords:
- _tmktemp_s function
- mktemp_s function
- _wmktemp_s function
- _mktemp_s function
- files [C++], temporary
- tmktemp_s function
- wmktemp_s function
- temporary files [C++]
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
caps.latest.revision: 23
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
ms.openlocfilehash: 0497919857206342c75e998c7ee714f89bc066e5
ms.lasthandoff: 02/24/2017

---
# <a name="mktemps-wmktemps"></a>_mktemp_s, _wmktemp_s
Создает уникальное имя файла. Это версии функции [_mktemp, _wmktemp](../../c-runtime-library/reference/mktemp-wmktemp.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _mktemp_s(  
   char *template,  
   size_t sizeInChars  
);  
errno_t _wmktemp_s(  
   wchar_t *template,  
   size_t sizeInChars  
);  
template <size_t size>  
errno_t _mktemp_s(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
errno_t _wmktemp_s(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 `template`  
 Шаблон имени файла.  
  
 `sizeInChars`  
 Размер буфера в однобайтовых символах в `_mktemp_s`, в расширенных символах в `_wmktemp_s`, включая знак завершения NULL.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Обе этих функции возвращают нулевое значение в случае успешного выполнения; код ошибки — в случае сбоя.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`template`|`sizeInChars`|**возвращаемое значение**|**новое значение в шаблоне**|  
|----------------|-------------------|----------------------|-------------------------------|  
|`NULL`|любые|`EINVAL`|`NULL`|  
|Неверный формат (сведения о правильном формате см. в разделе `Remarks`)|любые|`EINVAL`|пустая строка|  
|any|<= количество X|`EINVAL`|пустая строка|  
  
 Если выполняется какое-либо из приведенных выше условий возникновения ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, для параметра `errno` устанавливается значение `EINVAL`, и функция возвращает значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_mktemp_s` создает уникальное имя файла, изменяя аргумент `template` таким образом, чтобы после вызова указатель `template` ссылался на строку, содержащую имя нового файла. Функция `_mktemp_s` автоматически требуемым образом обрабатывает аргументы в виде многобайтовых строк, распознавая многобайтовые последовательности символов в соответствии с текущей многобайтовой кодовой страницей, используемой системой времени выполнения. Функция `_wmktemp_s` — это версия `_mktemp_s` с расширенными символами; аргумент `_wmktemp_s` — строка расширенных символов. В остальных отношениях поведение функций `_wmktemp_s` и `_mktemp_s` идентично, за исключением того, что функция `_wmktemp_s` не обрабатывает многобайтовые строки.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmktemp_s`|`_mktemp_s`|`_mktemp_s`|`_wmktemp_s`|  
  
 Аргумент `template` имеет форму `baseXXXXXX`, где `base` является частью нового имени файла, который вы указали, а X — это заполнитель для символа, указанного в `_mktemp_s`. Каждый символ заполнителя в функции `template` должен быть обозначен символом X в верхнем регистре. Функция `_mktemp_s` сохраняет `base` и заменяет первый конечный символ X на букву. Функция `_mktemp_s` заменяет следующие конечные символы X пятизначным числом; это значение является уникальным номером, определяющим вызывающий процесс, а в многопоточных программах — вызывающий поток.  
  
 Каждый успешный вызов функции `_mktemp_s` изменяет `template`. В каждом последующем вызове из того же процесса или потока с таким же аргументом `template` функция `_mktemp_s` проверяет имена файлов, совпадающих с именами, которые были возвращены `_mktemp_s` в предыдущих вызовах. Если файл не существует для указанного имени, функция `_mktemp_s` возвращает это имя. Если файлы существуют для всех ранее возвращенных имен, функция `_mktemp_s` создает новое имя, заменяя букву, которая использовалась в ранее возвращенном имени, следующей доступной строчной буквой по порядку от "a" до "z". Например, если `base` — это  
  
```  
fn  
```  
  
 а пятизначное число, предоставляемое `_mktemp_s`, — 12345, то возвращается имя:  
  
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
  
 Функция `_mktemp_s` может создать до 26 уникальных имен файлов для любого заданного сочетания значений базы и шаблона. Таким образом, FNZ12345 является последним уникальным именем файла, которое может создать функция `_mktemp_s` для значений `base` и `template`, используемых в этом примере.  
  
 В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_mktemp_s`|\<io.h>|  
|`_wmktemp_s`|\<io.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_mktemp_s.cpp  
/* The program uses _mktemp to create  
 * five unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
  
char *fnTemplate = "fnXXXXXX";  
char names[5][9];  
  
int main()  
{  
   int i, err, sizeInChars;  
   FILE *fp;  
  
   for( i = 0; i < 5; i++ )  
   {  
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );  
      /* Get the size of the string and add one for the null terminator.*/  
      sizeInChars = strnlen(names[i], 9) + 1;  
      /* Attempt to find a unique filename: */  
      err = _mktemp_s( names[i], sizeInChars );  
      if( err != 0 )  
         printf( "Problem creating the template" );  
      else  
      {  
         if( fopen_s( &fp, names[i], "w" ) == 0 )  
            printf( "Unique filename is %s\n", names[i] );  
         else  
            printf( "Cannot open %s\n", names[i] );  
         fclose( fp );  
      }  
   }  
  
   return 0;  
}  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
Unique filename is fna03188  
Unique filename is fnb03188  
Unique filename is fnc03188  
Unique filename is fnd03188  
Unique filename is fne03188  
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
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)
