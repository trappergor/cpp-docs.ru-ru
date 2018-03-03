---
title: "Ошибка компилятора C3094 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3094
dev_langs:
- C++
helpviewer_keywords:
- C3094
ms.assetid: 10da9b7c-e72d-4013-9925-c83e1bb142db
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c50bdc1f6e2b7a3361c2bb316723b993e7f7a774
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3094"></a>Ошибка компилятора C3094
"атрибут": анонимное использование не допускается  
  
 Неправильно задана область действия атрибута.  Дополнительные сведения см. в разделе [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3094:  
  
```  
// C3094.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::Class)]  
public ref class AAttribute : Attribute {};  
  
[A];   // C3094  
  
// OK  
[A]  
ref class x{};  
```