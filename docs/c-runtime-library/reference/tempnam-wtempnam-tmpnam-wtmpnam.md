---
title: "_tempnam, _wtempnam, tmpnam, _wtmpnam | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wtempnam
- _wtmpnam
- tmpnam
- _tempnam
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
- wtempnam
- _wtmpnam
- wtmpnam
- tmpnam
- _wtempnam
- _tempnam
dev_langs: C++
helpviewer_keywords:
- wtempnam function
- file names [C++], creating temporary
- _tempnam function
- ttmpnam function
- tmpnam function
- tempnam function
- wtmpnam function
- temporary files, creating
- file names [C++], temporary
- _ttmpnam function
- _wtmpnam function
- _wtempnam function
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9708c23fc76095a591a2eceafcb875ce173383ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tempnam-wtempnam-tmpnam-wtmpnam"></a>_tempnam, _wtempnam, tmpnam, _wtmpnam
Формирует имена, которые можно использовать для создания временных файлов. Существуют более безопасные версии этих функций; см. статью [tmpnam_s, _wtmpnam_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *_tempnam(  
   const char *dir,  
   const char *prefix   
);  
wchar_t *_wtempnam(  
   const wchar_t *dir,  
   const wchar_t *prefix   
);  
char *tmpnam(  
   char *str   
);  
wchar_t *_wtmpnam(  
   wchar_t *str   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `prefix`  
 Строка, которая добавляется в начало имен, возвращаемых `_tempnam`.  
  
 `dir`  
 Путь, используемый в имени файла, если переменная среды TMP отсутствует или TMP не является допустимым каталогом.  
  
 `str`  
 Указатель, который будет содержать формируемое имя и совпадать с именем, возвращенным функцией. Это удобный способ сохранения формируемого имени.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает указатель на формируемое имя или `NULL` в случае сбоя. Сбой может возникать при попытке более `TMP_MAX` (STDIO см. H) вызовов с `tmpnam` или если вы используете `_tempnam` и указано недопустимое имя каталога в переменной среды TMP и `dir` параметра.  
  
> [!NOTE]
>  Указатели, возвращенные функциями `tmpnam` и `_wtmpnam`, указывают на внутренние статические буфера. Для освобождения этих указателей не следует вызывать функцию [free](../../c-runtime-library/reference/free.md). Функцию `free` необходимо вызывать для указателей, размещенных в памяти функциями `_tempnam` и `_wtempnam`.  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций возвращает имя файла, который в данный момент не существует. Функция `tmpnam` возвращает имя, уникальное в текущей рабочей папке, а функция `_tempnam` позволяет сформировать уникальное имя в папке, отличной от текущей. Заметьте, что если в начало имени файла добавляется обратная косая черта без сведений о пути, например \fname21, это означает, что имя является допустимым для текущей рабочей папки.  
  
 В случае функции `tmpnam` это сформированное имя файла можно сохранить в параметре `str`. Если параметр `str` имеет значение `NULL`, функция `tmpnam` оставляет результат во внутреннем статическом буфере. Поэтому все последующие вызовы уничтожают это значение. Имя, сформированное функцией `tmpnam`, состоит из программно формируемого имени файла и, после первого вызова функции `tmpnam`, расширения файла из последовательных чисел с основанием 32 (.1–.vvu, если параметр `TMP_MAX` в файле STDIO.H имеет значение 32 767).  
  
 Функция `_tempnam` формирует уникальное имя файла для каталога, выбранного по следующим правилам:  
  
-   Если переменная среды TMP определена и в ней задано допустимое имя каталога, уникальные имена файлов формируются для указанного каталога TMP.  
  
-   Если переменная среды TMP не определена или если в ней задано имя несуществующего каталога, функция `_tempnam` будет использовать параметр `dir` в качестве пути, для которого формируются уникальные имена.  
  
-   Если переменная среды TMP не указана или в ней указано имя несуществующего каталога, а параметр `dir` имеет значение `NULL` или содержит имя несуществующего каталога, для формирования уникальных имен функция `_tempnam` будет использовать текущий рабочий каталог. В настоящее время если и TMP, и `dir` содержат имена несуществующих каталогов, вызов функции `_tempnam` завершится ошибкой.  
  
 Имя, возвращаемое функцией `_tempnam`, будет объединением параметра `prefix` и последовательного порядкового номера, образующих уникальное имя файла в указанном каталоге. Функция `_tempnam` формирует имена файлов, не имеющие расширение. Функция `_tempnam` использует функцию [malloc](../../c-runtime-library/reference/malloc.md), чтобы выделить память для имени файла; программа отвечает за освобождение этого пространства, когда оно больше не нужно.  
  
 Функции `_tempnam` и `tmpnam` автоматически корректно обрабатывают многобайтовые строковые аргументы, распознавая последовательности многобайтовых символов согласно кодовой странице OEM, полученной из операционной системы. `_wtempnam` — это версия функции `_tempnam` для расширенных символов; аргументы и возвращаемое значение функции `_wtempnam` являются строками с расширенными символами. В остальных отношениях поведение функций `_wtempnam` и `_tempnam` идентично, за исключением того, что функция `_wtempnam` не обрабатывает многобайтовые строки. `_wtmpnam` — это версия с расширенными символами для `tmpnam`; аргумент и возвращаемое значение `_wtmpnam` являются строками с расширенными символами. В остальных отношениях поведение функций `_wtmpnam` и `tmpnam` идентично, за исключением того, что функция `_wtmpnam` не обрабатывает многобайтовые строки.  
  
 Если определены `_DEBUG` и `_CRTDBG_MAP_ALLOC`, функции `_tempnam` и `_wtempnam` заменяются вызовами функций [_tempnam_dbg и _wtempnam_dbg](../../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttmpnam`|`tmpnam`|`tmpnam`|`_wtmpnam`|  
|`_ttempnam`|`_tempnam`|`_tempnam`|`_wtempnam`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_tempnam`|\<stdio.h>|  
|`_wtempnam`, `_wtmpnam`|\<stdio.h> или \<wchar.h>|  
|`tmpnam`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_tempnam.c  
// compile with: /W3  
// This program uses tmpnam to create a unique filename in the  
// current working directory, then uses _tempnam to create   
// a unique filename with a prefix of stq.   
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char* name1 = NULL;  
   char* name2 = NULL;  
  
   // Create a temporary filename for the current working directory:   
   if( ( name1 = tmpnam( NULL ) ) != NULL ) // C4996  
   // Note: tmpnam is deprecated; consider using tmpnam_s instead  
      printf( "%s is safe to use as a temporary file.\n", name1 );  
   else  
      printf( "Cannot create a unique filename\n" );  
  
   // Create a temporary filename in temporary directory with the  
   // prefix "stq". The actual destination directory may vary  
   // depending on the state of the TMP environment variable and  
   // the global variable P_tmpdir.     
  
   if( ( name2 = _tempnam( "c:\\tmp", "stq" ) ) != NULL )  
      printf( "%s is safe to use as a temporary file.\n", name2 );   
   else  
      printf( "Cannot create a unique filename\n" );  
  
   // When name2 is no longer needed :     
   if(name2)  
     free(name2);  
  
}  
```  
  
```Output  
\s1gk. is safe to use as a temporary file.  
C:\DOCUME~1\user\LOCALS~1\Temp\2\stq2 is safe to use as a temporary file.  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)