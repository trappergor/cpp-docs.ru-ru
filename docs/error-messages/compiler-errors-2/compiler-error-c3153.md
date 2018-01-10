---
title: "Ошибка компилятора C3153 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3153
dev_langs: C++
helpviewer_keywords: C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af6ade83cd2c9d7f40303669bb39ce746fe75ccf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
