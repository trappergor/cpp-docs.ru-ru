---
title: "strerror, _strerror, _wcserror, __wcserror | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strerror"
  - "_strerror"
  - "_wcserror"
  - "__wcserror"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__sys_errlist"
  - "wcserror"
  - "_strerror"
  - "__wcserror"
  - "strerror"
  - "__sys_nerr"
  - "_tcserror"
  - "_wcserror"
  - "tcserror"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__sys_errlist"
  - "__sys_nerr"
  - "__wcserror - функция"
  - "_strerror - функция"
  - "_tcserror - функция"
  - "_wcserror - функция"
  - "сообщения об ошибках, получение"
  - "сообщения об ошибках, печать"
  - "печать сообщений об ошибках"
  - "strerror - функция"
  - "tcserror - функция"
  - "wcserror - функция"
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# strerror, _strerror, _wcserror, __wcserror
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает системную строку сообщения об ошибке \(`strerror`, `_wcserror`\) или форматирует пользовательскую строку сообщения об ошибке \(`_strerror`, `__wcserror`\).  Существуют более безопасные версии этих функций; см. раздел [strerror\_s, \_strerror\_s, \_wcserror\_s, \_\_wcserror\_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md).  
  
## Синтаксис  
  
```  
char *strerror(    int errnum  ); char *_strerror(    const char *strErrMsg  ); wchar_t * _wcserror(    int errnum  ); wchar_t * __wcserror(    const wchar_t *strErrMsg  );  
```  
  
#### Параметры  
 `errnum`  
 Номер ошибки.  
  
 `strErrMsg`  
 Пользовательское сообщение.  
  
## Возвращаемое значение  
 Все эти функции возвращают указатель на строку сообщения об ошибке.  Последующие вызовы могут перезаписать строку.  
  
## Заметки  
 Функция `strerror` сопоставляет `errnum` со строкой сообщения об ошибке и возвращает указатель на строку.  Фактически ни `strerror`, ни `_strerror` не печатают сообщение. Для этого необходимо вызвать функцию вывода, такую как [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md):  
  
```  
if (( _access( "datafile",2 )) == -1 )  
   fprintf( stderr, _strerror(NULL) );  
```  
  
 Если `strErrMsg` передается как `NULL`, `_strerror` возвращает указатель на строку, которая содержит системное сообщение об ошибке для последнего вызова библиотеки, который создал ошибку.  Строка сообщения об ошибке оканчивается символом новой строки \('\\n'\).  Если значение `strErrMsg` не равно `NULL`, `_strerror` возвращает указатель на строку, содержащую \(по порядку\) сообщение строки, двоеточие, пробел, системное сообщение об ошибке для последнего вызова библиотеки, создавшего ошибку, и символ новой строки.  Длина сообщения строки не должна превышать 94 символа.  
  
 Фактический номер ошибки для `_strerror` хранится в переменной [errno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  Чтобы обеспечить точные результаты, вызывайте `_strerror` сразу после того, как подпрограмма библиотеки возвращает ошибку.  В противном случае последующие вызовы `strerror` или `_strerror` могут перезаписать значение `errno`.  
  
 `_wcserror` и `__wcserror` — это версии `strerror` и `_strerror` с расширенными символами.  
  
 `_strerror`, `_wcserror` и `__wcserror` не входят в определение ANSI. Они являются расширениями Майкрософт, и мы не рекомендуем использовать их в ситуациях, когда требуется создать переносимый код.  Для совместимости с ANSI вместо них рекомендуется использовать `strerror`.  
  
 Для получения строк ошибок рекомендуется использовать `strerror` или `_wcserror` вместо нерекомендуемых макросов [\_sys\_errlist](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) и [\_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) и внутренних функций `__sys_errlist` и `__sys_nerr`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcserror`|`strerror`|`strerror`|`_wcserror`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strerror`|\<string.h\>|  
|`_strerror`|\<string.h\>|  
|`_wcserror`, `__wcserror`|\<string.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 См. пример для [perror](../../c-runtime-library/reference/perror-wperror.md).  
  
## Эквивалент в .NET Framework  
 [System::Exception::Message](https://msdn.microsoft.com/en-us/library/system.exception.message.aspx)  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)