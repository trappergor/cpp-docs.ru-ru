---
title: "strcat_s, wcscat_s, _mbscat_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strcat_s"
  - "_mbscat_s"
  - "wcscat_s"
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
  - "strcat_s"
  - "wcscat_s"
  - "_mbscat_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbscat_s - функция"
  - "дополнение строк"
  - "mbscat_s - функция"
  - "strcat_s - функция"
  - "строки [C++], присоединение"
  - "wcscat_s - функция"
ms.assetid: 0f2f9901-c5c5-480b-98bc-f8f690792fc0
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# strcat_s, wcscat_s, _mbscat_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Добавляет строку.  В этих версиях [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md) усовершенствована безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
> [!IMPORTANT]
>  `_mbscat_s` невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
errno_t strcat_s(  
   char *strDestination,  
   size_t numberOfElements,  
   const char *strSource   
);  
errno_t wcscat_s(  
   wchar_t *strDestination,  
   size_t numberOfElements,  
   const wchar_t *strSource   
);  
errno_t _mbscat_s(  
   unsigned char *strDestination,  
   size_t numberOfElements,  
   const unsigned char *strSource   
);  
template <size_t size>  
errno_t strcat_s(  
   char (&strDestination)[size],  
   const char *strSource   
); // C++ only  
template <size_t size>  
errno_t wcscat_s(  
   wchar_t (&strDestination)[size],  
   const wchar_t *strSource   
); // C++ only  
template <size_t size>  
errno_t _mbscat_s(  
   unsigned char (&strDestination)[size],  
   const unsigned char *strSource   
); // C++ only  
```  
  
#### Параметры  
 `strDestination`  
 Буфер строки назначения с завершающим null.  
  
 `numberOfElements`  
 Размер буфера строки назначения.  
  
 `strSource`  
 Буфер строки источника с нулевым завершением.  
  
## Возвращаемое значение  
 Нуль, если успешно; код ошибки при неудаче.  
  
### Условия возникновения ошибки  
  
|`strDestination`|`numberOfElements`|`strSource`|Возвращаемое значение|Содержимое `strDestination`.|  
|----------------------|------------------------|-----------------|---------------------------|----------------------------------|  
|`NULL` или без признака завершения|any|any|`EINVAL`|без изменений|  
|any|any|`NULL`|`EINVAL`|`strDestination`\[0\] задан равным 0|  
|any|0 или слишком мало|any|`ERANGE`|`strDestination`\[0\] задан равным 0|  
  
## Заметки  
 Функция `strcat_s` добавляет `strSource` к `strDestination`, а затем к результирующей строке завершающий символ null.  Начальный символ `strSource` перезаписывает конечный символ null `strDestination`.  При перекрытии исходной и конечной строк поведение инструкции `strcat_s` не определено.  
  
 Обратите внимание, что второй параметр содержит полный размер буфера, а не оставшийся свободным:  
  
```  
char buf[16];  
strcpy_s(buf, 16, "Start");  
strcat_s(buf, 16, " End");               // Correct  
strcat_s(buf, 16 – strlen(buf), " End"); // Incorrect  
```  
  
 `wcscat_s` и `_mbscat_s` являются версиями функции `strcat_s` для расширенных и многобайтовых символов.  Аргументы и возвращаемое значение `wcscat_s` представляют собой двухбайтовые строки; аргументы и возвращаемое значение `_mbscat_s` представляют собой многобайтовые строки.  В остальных случаях эти три функции ведут себя идентично.  
  
 Если `strDestination` является указателем на null или не содержит завершающего null, или если `strSource` является `NULL` указателем, или если строка назначения недостаточного размера, то вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `EINVAL` и устанавливают для `errno` значение `EINVAL`.  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
 Отладочные версии этих функций сначала заполняют буфер значением 0xFD.  Для отключения данного поведения используйте [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcscat_s`|`strcat_s`|`_mbscat_s`|`wcscat_s`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`strcat_s`|\<string.h\>|  
|`wcscat_s`|\<string.h\> или \<wchar.h\>|  
|`_mbscat_s`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 См. пример кода в [strcpy\_s, wcscpy\_s, \_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md).  
  
## Эквивалент в .NET Framework  
 [System::String::Concat](https://msdn.microsoft.com/en-us/library/system.string.concat.aspx)  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)