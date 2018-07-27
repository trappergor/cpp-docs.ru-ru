---
title: Ошибка компилятора C2883 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2883
dev_langs:
- C++
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc3119db27127521f5078a5753bb82c82da381ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244951"
---
# <a name="compiler-error-c2883"></a>Ошибка компилятора C2883
«Имя»: объявление функции вступает в противоречие с «идентификатор», представленный с помощью объявления  
  
 Предпринята попытка определить функцию более одного раза. Первое определение выполнено из пространства имен с `using` объявления. Второй был локальное определение.  
  
 Следующий пример приводит к возникновению ошибки C2883:  
  
```  
// C2883.cpp  
namespace A {  
   void z(int);  
}  
  
int main() {  
   using A::z;  
   void z(int);   // C2883  z is already defined  
}  
```