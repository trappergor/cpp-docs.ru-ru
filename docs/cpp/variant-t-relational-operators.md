---
title: "Операторы отношения _variant_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::operator=="
  - "_variant_t.operator!="
  - "_variant_t::operator!="
  - "_variant_t.operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= - оператор"
  - "== - оператор, с конкретными объектами Visual C++"
  - "оператор !=, реляционные операторы"
  - "оператор !=, вариант"
  - "оператор ==, вариант"
  - "operator!=, реляционные операторы"
  - "operator!=, вариант"
  - "operator==, вариант"
  - "реляционные операторы, _variant_t - класс"
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Операторы отношения _variant_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Сравнивает два объекта `_variant_t` и определяет, равны ли они.  
  
## Синтаксис  
  
```  
  
      bool operator==(  
   const VARIANT& varSrc   
) const;  
bool operator==(  
   const VARIANT* pSrc   
) const;  
bool operator!=(  
   const VARIANT& varSrc   
) const;  
bool operator!=(  
   const VARIANT* pSrc   
) const;  
```  
  
#### Параметры  
 *varSrc*  
 Объект **VARIANT**, который необходимо сравнить с объектом `_variant_t`.  
  
 `pSrc`  
 Указатель на объект **VARIANT**, который необходимо сравнить с объектом `_variant_t`.  
  
## Возвращаемое значение  
 Возвращает значение **true**, если сравнение показало равенство, и **false** в противоположном случае.  
  
## Заметки  
 Сравнивает объект `_variant_t` с **VARIANT** и определяет, равны ли они.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_variant\_t](../cpp/variant-t-class.md)