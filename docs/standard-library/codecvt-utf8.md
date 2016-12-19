---
title: "codecvt_utf8 | Microsoft Docs"
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
  - "std.codecvt_utf8"
  - "std::codecvt_utf8"
  - "codecvt_utf8"
  - "codecvt/std::codecvt_utf8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf8 - класс"
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf8
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет аспект [locale](../standard-library/locale-class.md), который выполняет преобразование между расширенными символами кодированными в качестве UCS\-2 или UCS\-4, и поток байтов кодировкой как UTF\-8.  
  
## Синтаксис  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>  
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