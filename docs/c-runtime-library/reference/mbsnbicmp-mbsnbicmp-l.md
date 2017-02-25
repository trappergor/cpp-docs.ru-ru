---
title: "_mbsnbicmp, _mbsnbicmp_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbicmp_l"
  - "_mbsnbicmp"
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
  - "_strnicmp"
  - "_wcsnicmp_l"
  - "_mbsnbicmp"
  - "mbsnbicmp"
  - "mbsnbicmp_l"
  - "_tcsnicmp"
  - "_strnicmp_l"
  - "_tcsnicmp_l"
  - "_wcsnicmp"
  - "_mbsnbicmp_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbicmp - функция"
  - "_mbsnbicmp_l - функция"
  - "_strnicmp - функция"
  - "_strnicmp_l - функция"
  - "_tcsnicmp - функция"
  - "_tcsnicmp_l - функция"
  - "_wcsnicmp - функция"
  - "_wcsnicmp_l - функция"
  - "mbsnbicmp - функция"
  - "mbsnbicmp_l - функция"
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _mbsnbicmp, _mbsnbicmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сравнивает `n` байтов двух строк многобайтовых символов и не учитывает регистр.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows.  Дополнительные сведения см. в разделе [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _mbsnbicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
```  
  
#### Параметры  
 `string1, string2`  
 Строки с завершающим нулем для сравнения.  
  
 `count`  
 Число сравниваемых байтов.  
  
## Возвращаемое значение  
 Возвращаемое значение показывает связь между подстроками.  
  
|Возвращаемое значение|Описание|  
|---------------------------|--------------|  
|\< 0|Подстрока `string1` меньше, чем подстрока `string2`.|  
|0|Подстрока `string1` идентична подстроке `string2`.|  
|\> 0|Подстрока `string1` больше, чем подстрока `string2`.|  
  
 При ошибке `_mbsnbcmp` возвращает значение `_NLSCMPERROR`, которое определено в String.h и Mbstring.h.  
  
## Заметки  
 Функция `_mbsnbicmp` выполняет порядковое сравнение не более `count` первых байтов строк `string1` и `string2`.  Сравнение выполняется путем преобразования каждого символа в нижний регистр; `_mbsnbcmp` — версия `_mbsnbicmp`, учитывающая регистр.  Сравнение заканчивается, если был достигнут завершающий нуль\-символ в любой из строк до того, как были сравнены `count` симв.  Если строки равны, когда завершающий нуль\-символ достигается в любой из строк до того, как `count` симв. сравнены, более короткая строка считается меньшей.  
  
 Функция `_mbsnbicmp`  аналогична `_mbsnicmp` за исключением того, что она сравнивает строки по байтам \(до `count` байтов\), а не по символам.  
  
 Две строки, содержащие символы, которые расположены между Z и a в таблице ASCII \("\[", "\\", "\]", "^", "\_" и "\`"\), сравниваются по\-разному в зависимости от их регистра.  Например, две строки `ABCDE` и `ABCD^` сравниваются с одним результатом, если сравнение производится в нижнем регистре \(`abcde` \> `abcd^`\), и с другим, если сравнение производится в верхнем регистре \(`ABCDE` \< `ABCD^`\).  
  
 Функция `_mbsnbicmp` распознает последовательности многобайтовых символов в соответствии с текущей многобайтовой [кодовой страницей](../../c-runtime-library/code-pages.md).  На нее не влияет текущий параметр языкового стандарта.  
  
 Если `string1` или `string2` является пустым указателем, функция `_mbsnbicmp` вызывает обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, функция возвращает `_NLSCMPERROR` и устанавливает для параметра `errno` значение `EINVAL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsnicmp_l`|`_strnicmp_l`|`_mbsnbicmp_l`|`_wcsnicmp_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_mbsnbicmp`|\<mbstring.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
 См. пример для [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление строками](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_mbsnbcmp, \_mbsnbcmp\_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [\_stricmp, \_wcsicmp, \_mbsicmp, \_stricmp\_l, \_wcsicmp\_l, \_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)