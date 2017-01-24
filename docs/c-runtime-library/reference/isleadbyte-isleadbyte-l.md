---
title: "isleadbyte, _isleadbyte_l | Microsoft Docs"
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
  - "_isleadbyte_l"
  - "isleadbyte"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_istleadbyte"
  - "_isleadbyte_l"
  - "isleadbyte"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "старшие байты"
  - "_isleadbyte_l - функция"
  - "_istleadbyte - функция"
  - "istleadbyte - функция"
  - "isleadbyte - функция"
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isleadbyte, _isleadbyte_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет, является ли символ начальным байтом многобайтового символа.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int isleadbyte(  
   int c   
);  
int _isleadbyte_l(  
   int c   
);  
```  
  
#### Параметры  
 `c`  
 Проверяемое целое число.  
  
## Возвращаемое значение  
 `isleadbyte` возвращает ненулевое значение, если аргумент удовлетворяет условию теста, или значение 0 в противном случае. В языковом стандарте "C" и в языковых стандартах однобайтовой кодировки \(SBCS\) `isleadbyte` всегда возвращает значение 0.  
  
## Заметки  
 Макрос `isleadbyte` возвращает ненулевое значение, если его аргумент является первым байтом многобайтового символа.`isleadbyte` выдает значимый результат для любого целочисленного аргумента от –1 \(`EOF`\) до `UCHAR_MAX` \(0xFF\) включительно.  
  
 Ожидаемый тип аргумента `isleadbyte` — `int`. Если передается символ со знаком, компилятор может преобразовать его в целое число по расширению знака, создавая непредсказуемые результаты.  
  
 Версия этой функции с суффиксом `_l` идентична, однако для поведения, определяемого языковым стандартом, вместо текущего языкового стандарта в ней используется переданный языковой стандарт.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_istleadbyte`|Всегда возвращает значение false|**\_** `isleadbyte`|Всегда возвращает значение false|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`isleadbyte`|\<ctype.h\>|  
|`_isleadbyte_l`|\<ctype.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо, но см. раздел [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx).  
  
## См. также  
 [Классификация байтов](../../c-runtime-library/byte-classification.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Процедуры \_ismbb](../../c-runtime-library/ismbb-routines.md)