---
title: "Ошибка компилятора C2632 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2632
dev_langs: C++
helpviewer_keywords: C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c1af198d4949da112792c2bbddfac68a80d0daf4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2632"></a>Ошибка компилятора C2632
«тип1» и «тип2» не допускается  
  
 Эта ошибка может возникнуть, если отсутствует код между двумя спецификаторами.  
  
 Следующий пример приводит к возникновению ошибки C2632:  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 Эта ошибка может также возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003. `bool`является правильным типом. В предыдущих версиях `bool` представлял собой typedef, и можно было создать идентификаторы с таким именем.  
  
 Следующий пример приводит к возникновению ошибки C2632:  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 Чтобы устранить эту ошибку, чтобы код является допустимым в версиях Visual C++ для Visual Studio .NET 2003 и Visual Studio .NET, переименуйте идентификатор.