---
title: Ошибка компилятора C3748 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3748
dev_langs:
- C++
helpviewer_keywords:
- C3748
ms.assetid: 6fe71a0a-dd93-4ce6-9729-b9616360cf34
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de3d943db70b0e13b727f9c3e680f6cccc7f446e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274057"
---
# <a name="compiler-error-c3748"></a>Ошибка компилятора C3748
«интерфейс»: управляемые интерфейсы не могут порождать события  
  
 [__Event](../../cpp/event.md) ключевое слово не может отображаться внутри интерфейса.  
  
 Следующий пример приводит к возникновению ошибки C3748:  
  
```  
// C3748.cpp  
__interface I {  
// try the following line instead  
// struct I {  
   __event void f();   // C3748  
};  
  
int main() {  
}  
```