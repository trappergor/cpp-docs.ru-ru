---
title: "Ошибка компилятора C3153 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3153
dev_langs:
- C++
helpviewer_keywords:
- C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9d6a2ad948ae8d5517f7b98316b4e3c67bea5afb
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3153"></a>Ошибка компилятора C3153
«интерфейс»: невозможно создать экземпляр интерфейса  
  
 Не удается создать экземпляр интерфейса. Чтобы использовать члены интерфейса, создайте класс, наследующий интерфейс, реализуйте члены интерфейса и затем использовать элементы.  
  
 Следующий пример приводит к возникновению ошибки C3153:  
  
```  
// C3153.cpp  
// compile with: /clr  
interface class A {  
};  
  
int main() {  
   A^ a = gcnew A;   // C3153  
}  
```  

