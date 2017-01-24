---
title: "codecvt_utf16 | Microsoft Docs"
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
  - "codecvt/std::codecvt_utf16"
  - "std::codecvt_utf16"
  - "std.codecvt_utf16"
  - "codecvt_utf16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf16 - класс"
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет [языкового стандарта](../standard-library/locale-class.md) аспект, который выполняет преобразование между расширенных символов в кодировке UCS\-2 или UCS\-4 и поток байтов в кодировке UTF\-16LE или UTF\-16BE.  
  
## Синтаксис  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Elem`|Тип двухбайтового элемента.|  
|`Maxcode`|Максимальное количество символов для аспекта языкового стандарта.|  
|`Mode`|Сведения о конфигурации для аспекта языкового стандарта.|  
  
## Заметки  
 Этот класс шаблона преобразование расширенных символов в кодировке UCS\-2 или UCS\-4 и поток байтов в кодировке UTF\-16LE, если `Mode & little_endian`, или UTF\-16BE в противном случае.  
  
 Должен быть записан в поток байтов двоичный файл; могут быть повреждены при записи в текстовый файл.  
  
## Требования  
 **Заголовка:** \< codecvt \>  
  
 **Пространство имен:** std