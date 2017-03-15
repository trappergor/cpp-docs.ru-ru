---
title: "_bstr_t::operator ! | Microsoft Docs"
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
  - "_bstr_t::operator!"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "! оператор"
  - "Оператор !, bstr"
  - "operator!, bstr"
ms.assetid: 6e60b5a5-2d28-4eec-9e12-790da8f1fdd4
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::operator !
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Проверяет, является ли инкапсулированная строка `BSTR` пустой строкой \(**NULL**\).  
  
## Синтаксис  
  
```  
  
bool operator!( ) const throw( );  
  
```  
  
## Возвращаемое значение  
 Возвращается значение **true**, если да; в противном случае возвращается значение **false**.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_bstr\_t](../cpp/bstr-t-class.md)