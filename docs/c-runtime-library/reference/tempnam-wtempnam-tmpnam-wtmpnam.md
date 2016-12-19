---
title: "_tempnam, _wtempnam, tmpnam, _wtmpnam | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wtempnam"
  - "_wtmpnam"
  - "tmpnam"
  - "_tempnam"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wtempnam"
  - "_wtmpnam"
  - "wtmpnam"
  - "tmpnam"
  - "_wtempnam"
  - "_tempnam"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tempnam - функция"
  - "_ttmpnam - функция"
  - "_wtempnam - функция"
  - "_wtmpnam - функция"
  - "имена файлов [C++], создание временных"
  - "имена файлов [C++], временные"
  - "tempnam - функция"
  - "временные файлы, создание"
  - "tmpnam - функция"
  - "ttmpnam - функция"
  - "wtempnam - функция"
  - "wtmpnam - функция"
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _tempnam, _wtempnam, tmpnam, _wtmpnam
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Генерирует имя, которые можно использовать для создания временных файлов.  Существуют более безопасные версии некоторых из этих функций; см. раздел [tmpnam\_s, \_wtmpnam\_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md).  
  
## Синтаксис  
  
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
  
#### Параметры  
 `prefix`  
 Строка, которая будет добавлена к началу имен, возвращаемых функцией `_tempnam`.  
  
 `dir`  
 Путь, используемый в имени файла, если нет переменной среды TMP или если TMP не является допустимым каталогом.  
  
 `str`  
 Указатель, который содержит генерируемое имя и будет совпадать с именем, возвращенным функцией.  Это удобный способ сохранить генерируемое имя.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает указатель на создаваемое имя или `NULL` в случае сбоя.  Ошибка может возникать при попытке совершить больше, чем `TMP_MAX` \(см. STDIO.H\), вызовов с `tmpnam` или при использовании `_tempnam`, когда в переменной среды TMP и в параметре `dir` задана неверная директория.  
  
> [!NOTE]
>  Указатели, возвращенные `tmpnam` и `_wtmpnam` указывают на внутренние статические буфера.  [free](../../c-runtime-library/reference/free.md) не следует вызывать для освобождения этих указателей.  `free` необходимо вызывать для указателей, размещенных в памяти функциями `_tempnam` и `_wtempnam`.  
  
## Заметки  
 Каждая из этих функций возвращает имя файла, который в данный момент не существует.  `tmpnam` возвращает имя уникальное в текущей рабочей папке, а `_tempnam` позволяет сгенерировать уникальное имя в папке, отличной от текущей.  Заметьте, что если к началу имени файла приписывается обратная косая черта без сведений о пути, например \\fname21, это означает, что имя является допустимым для текущей рабочей папки.  
  
 Для `tmpnam` можно расположить это генерируемое имя в `str`.  Если `str` является `NULL`, `tmpnam` оставляет результат во внутреннем статическом буфере.  Таким образом все последующие вызовы уничтожают это значение.  Имя, сгенерированное `tmpnam`, состоит из программно генерируемого имени файла и, после первого вызова `tmpnam`, расширения файла из последовательности чисел c основанием 32 \(.1\-.vvu, когда `TMP_MAX` в STDIO.H равен 32,767\).  
  
 `_tempnam` создаст уникальное имя файла для выбранного каталога по следующим правилам:  
  
-   Если переменная среды TMP определена и установлена на допустимое имя каталога, уникальные имена файлов создаются для указанного TMP каталога.  
  
-   Если переменная среды TMP не указана или если она установлена на имя каталога, который не существует, то `_tempnam` будет использовать параметр `dir` в виде пути, для которого он генерирует уникальные имена.  
  
-   Если переменная среды TMP не указана или если ей установлено имя каталога, который не существует, и если `dir` имеет значение или `NULL`, или имя несуществующего каталога, то `_tempnam` будет использовать рабочую папку, чтобы генерировать уникальные имена.  В настоящее время, если и TMP, и `dir` содержат имена несуществующих каталогов, вызов функции `_tempnam` завершится ошибкой.  
  
 Имя, возвращаемое `_tempnam`, будет объединением `prefix` и последовательности чисел, объединенных для создания уникального имени файла в указанном каталоге.  `_tempnam` создает имена файлов, не имеющих расширение.  `_tempnam` использует [malloc](../../c-runtime-library/reference/malloc.md), чтобы выделить место для имени файла; программа отвечает за освобождение этого пространства, когда оно больше не нужно.  
  
 `_tempnam` и `tmpnam` автоматически корректно обрабатывают многобайтовые строковые аргументы, распознавая последовательности многобайтовых символов согласно кодовой странице изготовителя оборудования \(OEM\), полученной из операционной системы.  `_wtempnam` — это двухбайтовая версия функции `_tempnam`; аргументы и возвращаемое значение `_wtempnam` являются строками расширенных символов.  В остальных случаях поведение `_wtempnam` и `_tempnam` идентично, за исключением того, что `_wtempnam` не обрабатывает многобайтовые строки.  `_wtmpnam` — это двухбайтовая версия функции `tmpnam`; аргумент и возвращаемое значение `_wtmpnam` являются строками двухбайтовых символов.  В остальных случаях поведение `_wtmpnam` и `tmpnam` идентично, за исключением того, что `_wtmpnam` не обрабатывает многобайтовые строки.  
  
 Если `_DEBUG` и `_CRTDBG_MAP_ALLOC` определены, `_tempnam` и `_wtempnam` заменяются вызовом функции [\_tempnam\_dbg и \_wtempnam\_dbg](../../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_ttmpnam`|`tmpnam`|`tmpnam`|`_wtmpnam`|  
|`_ttempnam`|`_tempnam`|`_tempnam`|`_wtempnam`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_tempnam`|\<stdio.h\>|  
|`_wtempnam`, `_wtmpnam`|\<stdio.h\> или \<wchar.h\>|  
|`tmpnam`|\<stdio.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
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
  
  **\\s1gk. is safe to use as a temporary file.**  
**C:\\DOCUME~1\\user\\LOCALS~1\\Temp\\2\\stq2 is safe to use as a temporary file.**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)   
 [tmpfile\_s](../Topic/tmpfile_s.md)