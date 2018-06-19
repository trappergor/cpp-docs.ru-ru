---
title: Ошибка компилятора C2635 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2635
dev_langs:
- C++
helpviewer_keywords:
- C2635
ms.assetid: 9deca2a8-2d61-42eb-9783-6578132ee3fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30916834b8adee0d1a80625624e80c5a860e57ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233994"
---
# <a name="compiler-error-c2635"></a>Ошибка компилятора C2635
не удается преобразовать «идентификатор1 *» в "идентификатор2\*"; предполагается преобразование из виртуального базового класса  
  
 Для преобразования требуется приведение из `virtual` базового класса в производном классе не допускается.  
  
 Следующий пример приводит к возникновению ошибки C2635:  
  
```  
// C2635.cpp  
class B {};  
class D : virtual public B {};  
class E : public B {};  
  
int main() {  
   B b;  
   D d;  
   E e;  
  
   D * pD = &d;  
   E * pE = &e;  
   pD = (D*)&b;   // C2635  
   pE = (E*)&b;   // OK  
}  
```