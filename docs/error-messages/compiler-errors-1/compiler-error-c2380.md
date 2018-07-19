---
title: Ошибка компилятора C2380 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2380
dev_langs:
- C++
helpviewer_keywords:
- C2380
ms.assetid: 717b1e6e-ddfe-4bac-a5f3-7f9a4dcb1572
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa2d0fc361f1cf5ba5355ca11ce86279ebd3575f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33195637"
---
# <a name="compiler-error-c2380"></a>Ошибка компилятора C2380
типы перед «идентификатор» (конструктор с возвращаемым типом или недопустимое переопределение текущего имени класса?)  
  
 Конструктор возвращает значение или переопределяет имя класса.  
  
 При компиляции следующего примера возникнет ошибка C2326:  
  
```  
// C2380.cpp  
// compile with: /c  
class C {  
public:  
   int C();   // C2380, specifies an int return  
   int C;   // C2380, redefinition of i  
   C();   // OK  
};  
```