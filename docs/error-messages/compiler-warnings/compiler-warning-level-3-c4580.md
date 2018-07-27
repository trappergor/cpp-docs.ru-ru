---
title: Предупреждение (уровень 3) C4580 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4580
dev_langs:
- C++
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89ad08af77b62cd0992e9415e2df8b31233e4e0d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290986"
---
# <a name="compiler-warning-level-3-c4580"></a>Предупреждение компилятора (уровень 3) C4580
использовать [attribute] не рекомендуется; вместо этого в качестве базового класса укажите System::Attribute или Platform::Metadata  
  
[[атрибута](../../windows/attribute.md)] больше не является предпочтительным синтаксисом для создания пользовательских атрибутов. Дополнительные сведения см. в разделе [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md). Для кода CLR атрибуты должны быть производными от `System::Attribute`. Для кода среды выполнения Windows атрибуты должны быть производными от `Platform::Metadata`.  
  
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