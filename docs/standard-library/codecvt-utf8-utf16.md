---
title: "codecvt_utf8_utf16 | Microsoft Docs"
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
  - "codecvt_utf8_utf16"
  - "codecvt/std::cvt_utf8_utf16"
  - "std::codecvt_utf8_utf16"
  - "std.codecvt_utf8_utf16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf8_utf16 - класс"
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf8_utf16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет аспект [locale](../standard-library/locale-class.md), который выполняет преобразование между расширенными символами кодированными как UTF\-16 и байтовым потоком кодированным как UTF\-8.  
  
## Синтаксис  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Elem`|Тип элемента юникода.|  
|`Maxcode`|Максимальное количество символов для аспекта языкового стандарта.|  
|`Mode`|Сведения о конфигурации для аспекта языкового стандарта.|  
  
## Заметки  
 Можно записать в поток байтов или двоичный файл или текстовый файл.  
  
## Требования  
 **Заголовок:**\<codecvt\>  
  
 **Пространство имен:** std