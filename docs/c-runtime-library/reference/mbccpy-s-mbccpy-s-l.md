---
title: "_mbccpy_s, _mbccpy_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbccpy_s"
  - "_mbccpy_s_l"
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
apitype: "DLLExport"
f1_keywords: 
  - "_mbccpy_s_l"
  - "mbccpy_s_l"
  - "mbccpy_s"
  - "_mbccpy_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbccpy_s - функция"
  - "_mbccpy_s_l - функция"
  - "_tccpy_s - функция"
  - "_tccpy_s_l - функция"
  - "mbccpy_s - функция"
  - "mbccpy_s_l - функция"
  - "tccpy_s - функция"
  - "tccpy_s_l - функция"
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
caps.latest.revision: 30
caps.handback.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbccpy_s, _mbccpy_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Копирует один многобайтовый символ из строки в другую строку.  В этих версиях [\_mbccpy, \_mbccpy\_l](../Topic/_mbccpy,%20_mbccpy_l.md) усовершенствована безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
errno_t _mbccpy_s(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src   
);  
errno_t _mbccpy_s_l(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
);  
template <size_t size>  
errno_t _mbccpy_s(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src   
); // C++ only  
template <size_t size>  
errno_t _mbccpy_s_l(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
); // C++ only  
```  
  
#### Параметры  
 \[исходящий\] `dest`  
 Место назначения копирования.  
  
 \[входящий\] `buffSizeInBytes`  
 Размер буфера назначения.  
  
 \[исходящий\] `pCopied`  
 Заполнен количеством копированных байтов \(1 или 2 в случае успешного выполнения\).  Передайте `NULL`, это число не важно.  
  
 \[входящий\] `src`  
 Многобайтовый символ для копирования.  
  
 \[входящий\] `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Нуль, если успешно; код ошибки при неудаче.  Если `src` или `dest` равны `NULL`, или если больше `buffSizeinBytes` байтов будут скопированы в `dest`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `EINVAL`, и `errno` принимает значение `EINVAL`.  
  
## Заметки  
 Функция `_mbccpy_s` копирует один многобайтовый символ из `src` в `dest`.  Если `src` не указывает на старший байт многобайтового символа, что задано неявным вызовом [\_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md), то копируется один байт, на который указывает `src`.  Если `src` указывает на старший байт, но следующий байт равен 0 и поэтому недопустим, то 0 копируется в `dest`, `errno` принимает значение `EILSEQ`, и функция возвращает `EILSEQ`.  
  
 `_mbccpy_s` не добавляет завершающий нуль\-символ; однако если `src` указывает на нуль\-символ, то он копируется в `dest` \(это просто обычное однобайтовое копирование\).  
  
 Значение в `pCopied` равно количеству копированных байтов.  Возможные значения 1 и 2, если операция выполнена успешно.  Если передается `NULL`, то этот параметр не учитывается.  
  
|`src`|скопированный в `dest`|`pCopied`|Возвращаемое значение|  
|-----------|----------------------------|---------------|---------------------------|  
|не\-ведущий байт|не\-ведущий байт|1|0|  
|0|0|1|0|  
|старший байт, за которым следует не 0|старший байт, за которым следует не 0|2|0|  
|старший байт, за которым следует 0|0|1|`EILSEQ`|  
  
 Обратите внимание, что вторая строка \- это только особый случай первой.  Также обратите внимание, что таблица предполагает, что `buffSizeInBytes` \>\= `pCopied`.  
  
 `_mbccpy_s` использует текущий языковой стандарт для любого поведения, зависимого от языкового стандарта.  `_mbccpy_s_l` совпадает с `_mbccpy_s` за исключением того, что `_mbccpy_s_l` используется языковой стандарт, переданный для любого поведения, зависящего от языкового стандарта.  
  
 В C\+\+ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устранена необходимость указывать аргумент size.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tccpy_s`|Сопоставляется макросу или встроенной функции.|`_mbccpy_s`|Сопоставляется макросу или встроенной функции.|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_mbccpy_s`|\<mbstring.h\>|  
|`_mbccpy_s_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)