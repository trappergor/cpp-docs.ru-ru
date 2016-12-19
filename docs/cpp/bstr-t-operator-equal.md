---
title: "_bstr_t::operator = | Microsoft Docs"
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
  - "_bstr_t::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= - оператор, с конкретными объектами Visual C++"
  - "оператор =, bstr"
  - "operator=, bstr"
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::operator =
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Присваивает новое значение существующему объекту `_bstr_t`.  
  
## Синтаксис  
  
```  
  
      _bstr_t& operator=(  
   const _bstr_t& s1   
) throw ( );  
_bstr_t& operator=(  
   const char* s2   
);  
_bstr_t& operator=(  
   const wchar_t* s3   
);  
_bstr_t& operator=(  
   const _variant_t& var   
);  
```  
  
#### Параметры  
 *s1*  
 Объект `_bstr_t`, который требуется присвоить существующему объекту `_bstr_t`.  
  
 *s2*  
 Многобайтовая строка, которую требуется присвоить существующему объекту `_bstr_t`.  
  
 `s3`  
 Строка Юникода, которую требуется присвоить существующему объекту `_bstr_t`.  
  
 `var`  
 Объект `_variant_t`, который требуется присвоить существующему объекту `_bstr_t`.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## Пример  
 Пример использования функции `operator=` см. в разделе [\_bstr\_t::Assign](../cpp/bstr-t-assign.md).  
  
## См. также  
 [Класс \_bstr\_t](../cpp/bstr-t-class.md)