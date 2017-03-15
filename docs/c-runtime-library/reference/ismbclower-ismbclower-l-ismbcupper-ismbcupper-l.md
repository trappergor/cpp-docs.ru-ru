---
title: "_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ismbclower"
  - "_ismbclower_l"
  - "_ismbcupper_l"
  - "_ismbcupper"
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
  - "_ismbcupper"
  - "_ismbclower"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ismbclower - функция"
  - "_ismbclower_l - функция"
  - "_ismbcupper - функция"
  - "_ismbcupper_l - функция"
  - "ismbclower - функция"
  - "ismbclower_l - функция"
  - "ismbcupper - функция"
  - "ismbcupper_l - функция"
ms.assetid: 17d89587-65bc-477c-ba8f-a84e63cf59e7
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли многобайтовый символ символом в нижнем или верхнем регистре.  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _ismbclower(  
   unsigned int c   
);  
int _ismbclower_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcupper(  
   unsigned int c   
);  
int _ismbcupper_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `c`  
 Символ, который требуется проверить.  
  
 `locale`  
 Языковой стандарт, который необходимо использовать.  
  
## Возвращаемое значение  
 Каждая из этих процедур возвращает ненулевое значение, если символ удовлетворяет условию теста, или 0, если не удовлетворяет.  Если `c`\<\= 255 и есть соответствующая процедура `_ismbb` \(например, `_ismbcalnum` соответствует `_ismbbalnum`\), то результат равен возвращаемому значению соответствующей процедуры `_ismbb`.  
  
## Заметки  
 Каждая из этих функций проверяет определенный многобайтовый символ на соответствие заданному условию.  
  
 Версии этих функций с суффиксом `_l` идентичны, за исключением того, что для поведения, зависящего от языкового стандарта, они используют переданный параметр языкового стандарта вместо текущего языкового стандарта.  Для получения дополнительной информации см. [Языковой стандарт](../../c-runtime-library/locale.md).  
  
|Подпрограмма|Условие теста|Пример кодовой страницы 932|  
|------------------|-------------------|---------------------------------|  
|`_ismbclower`|Буква в нижнем регистре|Возвращает отличное от нуля значение только в том случае, если `c` \- однобайтовое представление буквы нижнего регистра английского алфавита в кодировке ASCII: 0x61\<\=`c`\<\=0x7A.|  
|`_ismbclower_l`|Буква в нижнем регистре|Возвращает отличное от нуля значение только в том случае, если `c` \- однобайтовое представление буквы нижнего регистра английского алфавита в кодировке ASCII: 0x61\<\=`c`\<\=0x7A.|  
|`_ismbcupper`|Буква в верхнем регистре|Возвращает отличное от нуля значение только в том случае, если `c` \- однобайтовое представление буквы верхнего регистра английского алфавита в кодировке ASCII: 0x41\<\=`c`\<\=0x5A.|  
|`_ismbcupper_l`|Буква в верхнем регистре|Возвращает отличное от нуля значение только в том случае, если `c` \- однобайтовое представление буквы верхнего регистра английского алфавита в кодировке ASCII: 0x41\<\=`c`\<\=0x5A.|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_ismbclower`|\<mbstring.h\>|  
|`_ismbclower_l`|\<mbstring.h\>|  
|`_ismbcupper`|\<mbstring.h\>|  
|`_ismbcupper_l`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
  
-   [System::Char::IsLower](https://msdn.microsoft.com/en-us/library/system.char.islower.aspx)  
  
-   [System::Char::IsUpper](https://msdn.microsoft.com/en-us/library/system.char.isupper.aspx)  
  
## См. также  
 [Классификация символов](../../c-runtime-library/character-classification.md)   
 [Процедуры \_ismbc](../../c-runtime-library/ismbc-routines.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей в многобайтной кодировке](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)   
 [Процедуры \_ismbb](../../c-runtime-library/ismbb-routines.md)