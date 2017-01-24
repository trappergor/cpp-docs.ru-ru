---
title: "Конструктор HStringReference::HStringReference | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference"
dev_langs: 
  - "C++"
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Конструктор HStringReference::HStringReference
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Инициализирует новый экземпляр класса HStringReference.  
  
## Синтаксис  
  
```cpp  
  
    template<unsigned int sizeDest>  
    HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
    template<unsigned int sizeDest>  
    HStringReference(wchar_t const (&str)[ sizeDest],   
unsigned int len)  
       throw();  
  
    HStringReference(HStringReference&& other) throw();  
  
```  
  
#### Параметры  
 `sizeDest`  
 Параметр шаблона, задающий размер буфера назначения HStringReference.  
  
 `str`  
 Ссылка на строку двубайтовых символов.  
  
 `len`  
 Максимальная длина буфера параметра `str`, используемая в данной операции.  Если параметр `len` не указан, то используется весь параметр `str`.  Если `len` больше, чем `sizeDest`, `len` установлено в `sizeDest`\-1.  
  
 `other`  
 Другой объект HStringReference.  
  
## Примечания  
 Первый конструктор инициализирует новый объект HStringReference того же размера, что и параметр `str`.  
  
 Второй конструктор инициализирует новый объект HStringReference, размер которого определен параметром `len`.  
  
 Третий конструктор инициализирует новый объект HStringReference значением параметра `other`, а затем удаляет параметр `other`.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)