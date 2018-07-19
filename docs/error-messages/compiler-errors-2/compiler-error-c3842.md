---
title: Ошибка компилятора C3842 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3842
dev_langs:
- C++
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c29878f7d64bfe1ed444130c77461dece6d20302
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270766"
---
# <a name="compiler-error-c3842"></a>Ошибка компилятора C3842
function: квалификаторы const и volatile для функций-членов управляемых типов или типов WinRT не поддерживаются  
  
 [const](../../cpp/const-cpp.md) и [volatile](../../cpp/volatile-cpp.md) не поддерживаются для функций-членов управляемых типов или типов среды выполнения Windows.  
  
 Следующий пример приводит к возникновению ошибки C3842:  
  
```  
// C3842a.cpp  
// compile with: /clr /c  
public ref struct A {  
   void f() const {}   // C3842  
   void f() volatile {}   // C3842  
  
   void f() {}  
};  
```