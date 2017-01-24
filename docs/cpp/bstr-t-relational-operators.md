---
title: "Операторы отношения _bstr_t | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::operator>"
  - "_bstr_t::operator=="
  - "_bstr_t::operator>="
  - "_bstr_t::operator!="
  - "_bstr_t::operator<"
  - "_bstr_t::operator<="
  - "_bstr_t::operator!"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= - оператор"
  - "< - оператор, сравнение конкретных объектов"
  - "<= - оператор, с конкретными объектами"
  - "== - оператор, с конкретными объектами Visual C++"
  - "> - оператор, сравнение конкретных объектов"
  - ">= - оператор, сравнение конкретных объектов"
  - "оператор !=, реляционные операторы"
  - "Оператор <, bstr"
  - "Оператор <=, bstr"
  - "оператор ==, bstr"
  - "Оператор >, bstr"
  - "Оператор >=, bstr"
  - "operator!=, реляционные операторы"
  - "operator<, bstr"
  - "operator<=, bstr"
  - "operator==, bstr"
  - "operator>=, bstr"
  - "реляционные операторы, _bstr_t - класс"
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Операторы отношения _bstr_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Сравнивает два объекта `_bstr_t`.  
  
## Синтаксис  
  
```  
  
      bool operator!( ) const throw( );   
bool operator==(  
   const _bstr_t& str   
) const throw( );  
bool operator!=(  
   const _bstr_t& str   
) const throw( );  
bool operator<(  
   const _bstr_t& str   
) const throw( );  
bool operator>(  
   const _bstr_t& str   
) const throw( );  
bool operator<=(  
   const _bstr_t& str   
) const throw( );  
bool operator>=(  
   const _bstr_t& str   
) const throw( );  
```  
  
## Заметки  
 Эти операторы производят лексикографическое сравнение двух объектов `_bstr_t` .  Операторы возвращают значение **true**, если сравнение верно; в противном случае возвращается значение **false**.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_bstr\_t](../cpp/bstr-t-class.md)