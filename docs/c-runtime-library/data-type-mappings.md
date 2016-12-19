---
title: "Сопоставления типов данных | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_TXCHAR"
  - "_TUCHAR"
  - "_TINT"
  - "_TSCHAR"
  - "_TCHAR"
  - "TCHAR::H"
  - "TCHAR"
  - "_T"
  - "_TEXT"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_T - тип"
  - "_TCHAR - тип"
  - "_TEXT - тип"
  - "_TINT - тип"
  - "_TSCHAR - тип"
  - "_TUCHAR - тип"
  - "_TXCHAR - тип"
  - "создание текстовых типов данных"
  - "T - тип"
  - "TCHAR - тип"
  - "типы данных TCHAR.H, сопоставления, определенные в"
  - "TEXT - тип"
  - "TINT - тип"
  - "TSCHAR - тип"
  - "TUCHAR - тип"
  - "TXCHAR - тип"
ms.assetid: 4e573c05-8800-468b-ae5f-76ff7409835e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Сопоставления типов данных
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти сопоставления типов данных определяются в TCHAR.H и зависят от того, была ли в вашей программе определена константа `_UNICODE` или `_MBCS`.  
  
 Дополнительные сведения см. в разделе [Использование типов данных TCHAR.H с кодом \_MBCS](../text/using-tchar-h-data-types-with-mbcs-code.md).  
  
### Универсальные текстовые сопоставления типов данных  
  
|Универсальный текст<br /><br /> Название типа данных|SBCS \(\_UNICODE,<br /><br /> \_MBCS не<br /><br /> определено\)|Символ \_MBCS<br /><br /> определение|\_UNICODE<br /><br /> определение|  
|--------------------------------------------------|------------------------------------------------------|-----------------------------------|-------------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_tfinddata_t`|`_finddata_t`|`_finddata_t`|`_wfinddata_t`|  
|`_tfinddata64_t`|`__finddata64_t`|`__finddata64_t`|`__wfinddata64_t`|  
|`_tfinddatai64_t`|`_finddatai64_t`|`_finddatai64_t`|`_wfinddatai64_t`|  
|`_TINT`|`int`|`int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` или `_TEXT`|Не действует \(удаляется препроцессором\)|Не действует \(удаляется препроцессором\)|`L` \(преобразовывает следующий символ или строку к его\(её\) аналогу в Юникоде\)|  
  
## См. также  
 [Универсальные текстовые сопоставления](../c-runtime-library/generic-text-mappings.md)   
 [Сопоставления констант и глобальных переменных](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [Сопоставления процедур](../c-runtime-library/routine-mappings.md)   
 [Пример программы, использующей обычный текст](../c-runtime-library/a-sample-generic-text-program.md)   
 [Использование универсальных текстовых сопоставлений](../c-runtime-library/using-generic-text-mappings.md)