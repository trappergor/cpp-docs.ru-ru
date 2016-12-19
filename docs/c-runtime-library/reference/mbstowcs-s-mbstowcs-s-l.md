---
title: "mbstowcs_s, _mbstowcs_s_l | Microsoft Docs"
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
  - "_mbstowcs_s_l"
  - "mbstowcs_s"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbstowcs_s_l"
  - "mbstowcs_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbstowcs_s_l - функция"
  - "mbstowcs_s - функция"
  - "mbstowcs_s_l - функция"
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
caps.latest.revision: 31
caps.handback.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mbstowcs_s, _mbstowcs_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Преобразование последовательности многобайтовых символов в соответствующую последовательность расширенных символов.  Версии [mbstowcs, \_mbstowcs\_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count   
);  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `pReturnValue`  
 Количество символов для преобразования.  
  
 \[исходящий\] `wcstr`  
 Адрес буфера для результирующей преобразованной строки расширенных символов.  
  
 \[входящий\] `sizeInWords`  
 Размер буфера `wcstr` в словах.  
  
 \[входящий\]`mbstr`  
 Адрес последовательности многобайтовых символов, завершенной нулевым символом.  
  
 \[входящий\] `count`  
 Максимальное количество расширенных символов, которые необходимо сохранить в буфере `wcstr`, не включая завершающий нулевой символ, или [\_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 \[входящий\] `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Нуль, если успешно; код ошибки при неудаче.  
  
|Условие ошибки.|Возвращает значение и `errno`|  
|---------------------|-----------------------------------|  
|`wcstr` содержит значение `NULL` и `sizeInWords` \> 0|`EINVAL`|  
|Параметр `mbstr` содержит значение `NULL`|`EINVAL`|  
|Буфер назначения слишком мал, чтобы вместить преобразованную строку \(иначе `count` будет `_TRUNCATE`; см. примечания ниже\)|`ERANGE`|  
|`wcstr` не должен быть `NULL` и `sizeInWords` \=\= 0|`EINVAL`|  
  
 Если срабатывает какое\-либо из этих условий, то возникает исключение о недопустимом параметре, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, то функция возвращает код ошибки и устанавливает `errno` как показано в таблице.  
  
## Заметки  
 Функция `mbstowcs_s` выполнит преобразование строки многобайтовых символов, содержащихся в `mbstr`, в расширенные, сохраняемые в буфере, на который указывает `wcstr`.  Преобразование будет продолжаться для каждого символа до тех пор, пока одно не будет выполнено одно из следующих условий:  
  
-   Встретился многобайтовый нулевой символ  
  
-   Встретился недопустимый многобайтовый символ  
  
-   Количество расширенных символов, хранящихся в буфере `wcstr`, равно `count`.  
  
 Строка назначения всегда содержит завершающий null \(даже в случае ошибки\).  
  
 Если `count` является специальным значением [\_TRUNCATE](../../c-runtime-library/truncate.md), то преобразование `mbstowcs_s` будет выполняться до тех пор, пока буфер назначения не будет заполнен с учетом завершающего признака null.  
  
 Если `mbstowcs_s` успешно выполнит преобразование исходной строки, то значение, содержащее размер преобразованной строки в расширенных символах с учетом завершающего нулевого символа конца строки, будет помещено в `*``pReturnValue` \(предоставленное значение `pReturnValue` не равно `NULL`\).  Это происходит даже если аргумент `wcstr` равен `NULL`, таким образом, предоставляя возможность задать необходимый размер буфера.  Обратите внимание, что если `wcstr` — `NULL`, то `count` игнорируется, а `sizeInWords` должен быть равен 0.  
  
 Если `mbstowcs_s` встречает недопустимый многобайтовый символ, он помещает 0 в `*``pReturnValue`, устанавливает буфер назначения в пустую строку, устанавливает `errno` в `EILSEQ` и возвращает `EILSEQ`.  
  
 Если последовательности, на которые указывают `mbstr` и `wcstr`, перекрываются, то поведение `mbstowcs_s` не определено.  
  
> [!IMPORTANT]
>  Убедитесь, что `wcstr` и `mbstr` не перекрываются, и что `count` правильно отражает количество многобайтовых символов для преобразования.  
  
 `mbstowcs_s` использует текущий языковой стандарт для любых расширений, зависящих от языкового стандарта; `_mbstowcs_s_l` идентична за исключением того, что она использует переданный языковой стандарт.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 В C\+\+ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера \(что исключает необходимость указания аргумента с размером буфера\), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`mbstowcs_s`|\<stdlib.h\>|  
|`_mbstowcs_s_l`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, \_mbtowc\_l](../Topic/mbtowc,%20_mbtowc_l.md)   
 [wcstombs, \_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)