---
title: Ошибка компилятора C2351 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2351
dev_langs:
- C++
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1660e5dfc4f17f7617c82eb3e633f345e2774495
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33222385"
---
# <a name="compiler-error-c2351"></a>Ошибка компилятора C2351
устаревший синтаксис инициализации конструктора C++  
  
 В списке инициализации нового стиля для конструктора необходимо явно задать имена каждого прямой базовый класс, даже если это только базовый класс.  
  
 Следующий пример приводит к возникновению ошибки C2351:  
  
```  
// C2351.cpp  
// compile with: /c  
class B {  
public:   
   B() : () {}   // C2351  
   B() {}   // OK  
};  
```