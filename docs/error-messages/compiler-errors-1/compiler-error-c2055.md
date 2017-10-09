---
title: "Ошибка компилятора C2055 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2055
dev_langs:
- C++
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c447d79179f3575230353b3db70717702b542b68
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2055"></a>Ошибка компилятора C2055
требуется список формальных параметров, а не список типов  
  
 Определение функции содержит список типов параметра, а не список формальных параметров. ANSI C требует формальных параметров, чтобы иметь имя, если они не являются пустыми или многоточием (`...`).  
  
 Следующий пример приводит к возникновению ошибки C2055:  
  
```  
// C2055.c  
// compile with: /c  
void func(int, char) {}  // C2055  
void func (int i, char c) {}   // OK  
```
