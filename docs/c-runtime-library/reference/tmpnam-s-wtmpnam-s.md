---
title: "tmpnam_s, _wtmpnam_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "tmpnam_s"
  - "_wtmpnam_s"
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
  - "tmpnam_s"
  - "_wtmpnam_s"
  - "L_tmpnam_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wtmpnam_s - функция"
  - "имена файлов [C++], создание временных"
  - "имена файлов [C++], временные"
  - "L_tmpnam_s - константа"
  - "временные файлы, создание"
  - "tmpnam_s - функция"
  - "wtmpnam_s - функция"
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# tmpnam_s, _wtmpnam_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Генерирует имя, которые можно использовать для создания временных файлов.  Здесь представлены версии [tmpnam and \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t tmpnam_s(  
   char * str,  
   size_t sizeInChars   
);  
errno_t _wtmpnam_s(  
   wchar_t *str,  
   size_t sizeInChars   
);  
template <size_t size>  
errno_t tmpnam_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wtmpnam_s(  
   wchar_t (&str)[size]  
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `str`  
 Указатель, содержащий генерируемое имя.  
  
 \[входящий\] `sizeInChars`  
 Размер буфера в символах.  
  
## Возвращаемое значение  
 Обе эти функции возвращают 0 при успешном завершении или номер ошибки при сбое.  
  
### Условия возникновения ошибки  
  
|||||  
|-|-|-|-|  
|`str`|`sizeInChars`|**Возвращаемое значение**|**Содержимое**  `str`|  
|`NULL`|any|`EINVAL`|без изменений|  
|не `NULL` \(указывает на допустимый адрес памяти\)|слишком короткий|`ERANGE`|без изменений|  
  
 Если параметр `str` имеет значение `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают `EINVAL`.  
  
## Заметки  
 Каждая из этих функций возвращает имя файла, который в данный момент не существует.  `tmpnam_s` возвращает имя, уникальное в текущей рабочей папке.  Заметьте, что если к началу имени файла приписывается обратная косая черта без сведений о пути, например \\fname21, это означает, что имя является допустимым для текущей рабочей папки.  
  
 Для `tmpnam_s` можно расположить это генерируемое имя в `str`.  Максимальная длина строки, возвращаемой `tmpnam_s`, равна `L_tmpnam_s`, как определено в STDIO.H.  Если `str` является `NULL`, `tmpnam_s` оставляет результат во внутреннем статическом буфере.  Таким образом все последующие вызовы уничтожают это значение.  Имя, сгенерированное `tmpnam_s`, состоит из программно генерируемого имени файла и, после первого вызова `tmpnam_s`, расширения файла из последовательности чисел в системе счисления с основанием 32 \(.1\-.1vvvvvu, когда `TMP_MAX_S` в STDIO.H равно INT\_MAX\).  
  
 `tmpnam_s` автоматически корректно обрабатывает многобайтовые строковые аргументы, распознавая последовательности многобайтовых символов согласно кодовой странице изготовителя оборудования \(OEM\), полученной из операционной системы.  `_wtmpnam_s` — это двухбайтовая версия функции `tmpnam_s`; аргумент и возвращаемое значение `_wtmpnam_s` являются строками двухбайтовых символов.  В остальных случаях поведение `_wtmpnam_s` и `tmpnam_s` идентично, за исключением того, что `_wtmpnam_s` не обрабатывает многобайтовые строки.  
  
 В C\+\+ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устранена необходимость указывать аргумент size.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_ttmpnam_s`|`tmpnam_s`|`tmpnam_s`|`_wtmpnam_s`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`tmpnam_s`|\<stdio.h\>|  
|`_wtmpnam_s`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_tmpnam_s.c  
// This program uses tmpnam_s to create a unique filename in the  
// current working directory.   
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char name1[L_tmpnam_s];  
   errno_t err;  
   int i;  
  
   for (i = 0; i < 15; i++)  
   {  
      err = tmpnam_s( name1, L_tmpnam_s );  
      if (err)  
      {  
         printf("Error occurred creating unique filename.\n");  
         exit(1);  
      }  
      else  
      {  
         printf( "%s is safe to use as a temporary file.\n", name1 );  
      }  
   }    
}  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile\_s](../Topic/tmpfile_s.md)