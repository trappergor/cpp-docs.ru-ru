---
title: "__pctype_func | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__pctype_func"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__pctype_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__pctype_func"
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# __pctype_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает указатель на массив данных о классификации символов.  
  
## Синтаксис  
  
```cpp  
const unsigned short *__pctype_func(  
   )  
```  
  
## Возвращаемое значение  
 Указатель на массив данных о классификации символов.  
  
## Заметки  
 Сведения в таблице классификации символов только для внутреннего пользования и используются различными функциями, которые классифицируют символы типа `char`.  Дополнительные сведения см. в подразделе `Remarks` раздела [\_pctype, \_pwctype, \_wctype, \_mbctype, \_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|\_\_pctype\_func|ctype.h|  
  
## См. также  
 [\_pctype, \_pwctype, \_wctype, \_mbctype, \_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)