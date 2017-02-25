---
title: "strerror_s, _strerror_s, _wcserror_s, __wcserror_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__wcserror_s"
  - "_strerror_s"
  - "_wcserror_s"
  - "strerror_s"
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
  - "wcserror_s"
  - "__wcserror_s"
  - "_tcserror_s"
  - "_wcserror_s"
  - "tcserror_s"
  - "strerror_s"
  - "_strerror_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wcserror_s - функция"
  - "_strerror_s - функция"
  - "_tcserror_s - функция"
  - "_wcserror_s - функция"
  - "сообщения об ошибках, получение"
  - "сообщения об ошибках, печать"
  - "печать сообщений об ошибках"
  - "strerror_s - функция"
  - "tcserror_s - функция"
  - "wcserror_s - функция"
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# strerror_s, _strerror_s, _wcserror_s, __wcserror_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает сообщение о системной ошибке \(`strerror_s`, `_wcserror_s`\) или печатает указанное пользователем сообщение об ошибке \(`_strerror_s`, `__wcserror_s`\).  Здесь представлены версии [strerror, \_strerror, \_wcserror, \_\_wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t _strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   const char *strErrMsg   
);  
errno_t _wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t __wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *strErrMsg   
);  
template <size_t size>  
errno_t strerror_s(  
   char (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t _strerror_s(  
   char (&buffer)[size],  
   const char *strErrMsg   
); // C++ only  
template <size_t size>  
errno_t _wcserror_s(  
   wchar_t (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t __wcserror_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *strErrMsg   
); // C++ only  
```  
  
#### Параметры  
 `buffer`  
 Буфер для хранения строки ошибок.  
  
 `numberOfElements`  
 Размер buffer.  
  
 `errnum`  
 Номер ошибки.  
  
 `strErrMsg`  
 Предоставленное пользователем сообщение.  
  
## Возвращаемое значение  
 Нуль, если успешно; код ошибки при неудаче.  
  
### Условия возникновения ошибки  
  
|`buffer`|`numberOfElements`|`strErrMsg`|Содержимое `buffer`.|  
|--------------|------------------------|-----------------|--------------------------|  
|`NULL`|any|any|Н\/Д|  
|any|0|any|без изменений|  
  
## Заметки  
 Функция `strerror_s` сопоставляет `errnum` в строку сообщения об ошибке, возвращая строку в `buffer`.  `_strerror_s` не принимает номер ошибки; он использует текущее значение `errno` для определения соответствующего сообщения.  Ни `strerror_s`, ни `_strerror_s` не печатает сообщения: Для этого необходимо вызвать функцию вывода, например [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md).  
  
```  
if (( _access( "datafile",2 )) == -1 )  
{  
   _strerror_s(buffer, 80);  
   fprintf( stderr, buffer );  
}  
```  
  
 Если `strErrMsg` равен `NULL`, `_strerror_s` возвращает строку в `buffer`, содержащий сообщение о системной ошибке для последнего вызова библиотеки, создавшего ошибку.  Строка сообщения об ошибке заканчивается символом новой строки \('\\n'\).  Если `strErrMsg` не равно `NULL`, то `_strerror_s` возвращает строку в `buffer`, содержащий \(в таком порядке\) строку сообщения, двоеточие, пробел, сообщение о системной ошибке для последнего вызова библиотеки, создавшего ошибку, и символ новой строки.  Строка сообщения может быть длиной не более 94 символа.  
  
 Эти функции усекают сообщение об ошибке, если его длина превышает `numberOfElements` \-1.  Результирующая строка в `buffer` всегда завершается символом null.  
  
 Фактический номер ошибки для `_strerror_s` хранится в переменной [errno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  Доступ к сообщениям о системной ошибке осуществляется через переменную [\_sys\_errlist](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md), которая представляет собой массив сообщений об ошибке, отсортированный по номеру ошибки.  `_strerror_s` получает доступ к соответствующему сообщению об ошибке, используя значение `errno` в качестве индекса для массива `_sys_errlist`.  Значение переменной [\_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) определено как максимальное количество элементов в массиве `_sys_errlist`.  Для предоставления точных результатов следует вызывать `_strerror_s` сразу после того, как библиотечная подпрограммы возвращается с ошибкой.  В противном случае последующие вызовы `strerror_s` или `_strerror_s` могут перезаписать значение `errno`.  
  
 `_wcserror_s` и `__wcserror_s`версии с расширенными символами функций `strerror_s`и `_strerror_s` соответственно.  
  
 Эти функции проверяют свои параметры.  Если буфер равен `NULL`, или если параметр размера равен 0, то вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `EINVAL` и устанавливают для `errno` значение `EINVAL`.  
  
 `_strerror_s, _wcserror_s,` и `__wcserror_s` не являются частью определения ANSI, а вместо этого они \- расширения Майкрософт для него.  Их не следует использовать там, где отдается предпочтение переносимости; для обеспечения совместимости с ANSI, используйте вместо них `strerror_s` .  
  
 В C\+\+ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устранена необходимость указывать аргумент size.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
 Отладочные версии этих функций сначала заполняют буфер значением 0xFD.  Для отключения данного поведения используйте [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcserror_s`|`strerror_s`|`strerror_s`|`_wcserror_s`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strerror_s`, `_strerror_s`|\<string.h\>|  
|`_wcserror_s`, `__wcserror_s`|\<string.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример для [perror](../../c-runtime-library/reference/perror-wperror.md).  
  
## Эквивалент в .NET Framework  
 [System::Exception::Message](https://msdn.microsoft.com/en-us/library/system.exception.message.aspx)  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)