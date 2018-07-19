---
title: Ошибка компилятора C2750 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2750
dev_langs:
- C++
helpviewer_keywords:
- C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06731b0b386b200b74697592137aac10a48a8e82
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233270"
---
# <a name="compiler-error-c2750"></a>Ошибка компилятора C2750
«Тип»: нельзя использовать «new» для ссылочного типа; Вместо этого использовать «gcnew»  
  
 Для создания экземпляра типа CLR, которое вызывает экземпляр должен располагаться в куче сбора мусора, необходимо использовать [gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C2750:  
  
```  
// C2750.cpp  
// compile with: /clr  
ref struct Y1 {};  
  
int main() {  
   Y1 ^ x = new Y1;   // C2750  
  
   // try the following line instead  
   Y1 ^ x2 = gcnew Y1;  
}  
```