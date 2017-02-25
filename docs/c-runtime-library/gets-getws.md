---
title: "gets, _getws | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getws"
  - "gets"
apilocation: 
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getts"
  - "gets"
  - "_getws"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_getts - функция"
  - "_getws - функция"
  - "gets - функция"
  - "getts - функция"
  - "getws - функция"
  - "линии, получение"
  - "стандартный ввод, чтение из"
  - "потоки, получение строк"
ms.assetid: 1ec2dd4b-f801-48ea-97c2-892590f16024
caps.latest.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# gets, _getws
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает строку из потока `stdin`. Существуют более безопасные версии этих функций; см. статью [gets\_s, \_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md).  
  
> [!IMPORTANT]
>  Эти функции устарели. Начиная с Visual Studio 2015 они недоступны в CRT. Безопасные версии этих функций, gets\_s и \_getws\_s, по\-прежнему доступны. Сведения об этих альтернативных функциях см. в статье [gets\_s, \_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md).  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
char *gets(   
   char *buffer   
);  
wchar_t *_getws(   
   wchar_t *buffer   
);  
template <size_t size>  
char *gets(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Параметры  
 `buffer`  
 Место хранения входной строки.  
  
## Возвращаемое значение  
 В случае успеха возвращает свой аргумент. Указатель `NULL` указывает на ошибку или конец файла. Используйте [ferror](../c-runtime-library/reference/ferror.md) или [feof](../c-runtime-library/reference/feof.md) для определения того, что именно произошло. Если параметр `buffer` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают `NULL` и устанавливают параметр errno в значение `EINVAL`.  
  
## Заметки  
 Функция `gets` считывает строку из стандартного потока ввода `stdin` и сохраняет ее в буфере `buffer`. Строка состоит из всех символов до первого символа новой строки \("\\n"\). Затем перед возвратом строки функция `gets` заменяет символ новой строки нуль\-символом \("\\0"\). Напротив, функция `fgets` сохраняет символ новой строки.`_getws` — это версия функции `gets` для расширенных символов; ее аргумент и возвращаемое значение являются строками расширенных символов.  
  
> [!IMPORTANT]
>  Поскольку нет возможности ограничить количество символов, считываемых функцией gets, недоверенный ввод может легко привести к переполнению буфера. Взамен рекомендуется использовать `fgets`.  
  
 В C\+\+ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Для получения дополнительной информации см. [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_getts`|`gets`|`gets`|`_getws`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`gets`|\<stdio.h\>|  
|`_getws`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_gets.c // compile with: /WX /W3 #include <stdio.h> int main( void ) { char line[21]; // room for 20 chars + '\0' gets( line );  // C4996 // Danger: No way to limit input to 20 chars. // Consider using gets_s instead. printf( "The line entered was: %s\n", line ); }  
```  
  
 Обратите внимание, что ввод более двадцати символов переполнит буфер строки и почти наверняка вызовет сбой программы.  
  
```Output  
  
Hello there!Текст введенной строки: Hello there! (Привет!)  
```  
  
## Эквивалент в .NET Framework  
 [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## См. также  
 [Потоковый ввод\-вывод](../c-runtime-library/stream-i-o.md)   
 [fgets, fgetws](../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs, fputws](../Topic/fputs,%20fputws.md)   
 [puts, \_putws](../Topic/puts,%20_putws.md)