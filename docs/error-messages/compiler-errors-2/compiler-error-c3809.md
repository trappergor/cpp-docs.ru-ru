---
title: Ошибка компилятора C3809 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3809
dev_langs:
- C++
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4b9fabec4da63bfe881e0020e99cd5c49a51789
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3809"></a>Ошибка компилятора C3809
class: управляемый тип или тип WinRT не может иметь дружественные функции, классы и интерфейсы  
  
 Управляемые типы и типы среды выполнения Windows не могут иметь дружественные элементы. Чтобы устранить эту ошибку, не объявляйте дружественные элементы внутри управляемых или типов среды выполнения Windows.  
  
 Следующий пример приводит к возникновению ошибки C3809:  
  
```  
// C3809a.cpp  
// compile with: /clr  
ref class A {};  
  
ref class B  
{  
public:  
   friend ref class A;   // C3809  
};  
  
int main()  
{  
}  
```