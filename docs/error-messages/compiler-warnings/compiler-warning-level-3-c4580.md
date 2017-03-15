---
title: "Предупреждение (уровень 3) C4580 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4580
dev_langs:
- C++
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: c8cebbda1d3472a2efda43f816e7a13f2f460408
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4580"></a>Предупреждение компилятора (уровень 3) C4580
использовать [attribute] не рекомендуется; вместо этого в качестве базового класса укажите System::Attribute или Platform::Metadata  
  
[[атрибута](../../windows/attribute.md)] больше не рекомендуется использовать синтаксис для создания пользовательских атрибутов. Дополнительные сведения см. в разделе [пользовательских атрибутов](../../windows/user-defined-attributes-cpp-component-extensions.md). Для кода CLR атрибуты должны быть производными от `System::Attribute`. Для кода среды выполнения Windows атрибуты должны быть производными от `Platform::Metadata`.  
  
## <a name="example"></a>Пример  
В следующем примере показано возникновение ошибки C3454 и приводятся сведения по ее устранению.  
  
```cpp  
// C4580.cpp  
// compile with: /W3 /c /clr  
[attribute]   // C4580  
public ref class Attr {  
public:  
   int m_t;  
};  
  
public ref class Attr2 : System::Attribute {  
public:  
   int m_t;  
};  
```
