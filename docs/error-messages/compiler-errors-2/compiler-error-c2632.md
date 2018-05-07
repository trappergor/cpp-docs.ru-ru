---
title: Ошибка компилятора C2632 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2632
dev_langs:
- C++
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3bc07c404a1f4d667045fdfea24009e7d20ad69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2632"></a>Ошибка компилятора C2632
«тип1» и «тип2» не допускается  
  
 Эта ошибка может возникнуть, если отсутствует код между двумя спецификаторами.  
  
 Следующий пример приводит к возникновению ошибки C2632:  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 Эта ошибка может также возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003. `bool` является правильным типом. В предыдущих версиях `bool` представлял собой typedef, и можно было создать идентификаторы с таким именем.  
  
 Следующий пример приводит к возникновению ошибки C2632:  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 Чтобы устранить эту ошибку, чтобы код является допустимым в версиях Visual C++ для Visual Studio .NET 2003 и Visual Studio .NET, переименуйте идентификатор.