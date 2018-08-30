---
title: Предупреждение компилятора (уровень 1) C4312 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4312
dev_langs:
- C++
helpviewer_keywords:
- C4312
ms.assetid: 541906ed-4f62-4bcb-947f-cf9ae7411bcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b30d020532935c925b1ecab25d17cd43a7e8663
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205906"
---
# <a name="compiler-warning-level-1-c4312"></a>Предупреждение компилятора (уровень 1) C4312
"операция": преобразование из "тип 1" в "тип 2" большего размера  
  
 Это предупреждение сообщает о попытке присвоить 32-разрядное значение 64-разрядному указателю, например при приведении 32-разрядного `int` или `long` к 64-разрядному указателю.  
  
 Это преобразование может быть небезопасным даже для значений указателей, которые помещаются в 32 бита, при расширении знака. Если отрицательное целое 32-разрядное число присваивается 64-разрядному указателю, расширение знака приводит к тому, что значение указателя ссылается на адрес в памяти, отличный от значения целого числа.  
  
 Это предупреждение возникает только для 64-разрядных целевых сред компиляции. Дополнительные сведения см. в разделе [правила использования указателей](/windows/desktop/WinProg64/rules-for-using-pointers).  
  
 В следующем примере кода возникает ошибка C4312 при компиляции для 64-разрядных сред.  
  
```  
// C4312.cpp  
// compile by using: cl /W1 /LD C4312.cpp  
void* f(int i) {  
   return (void*)i;   // C4312 for 64-bit targets  
}  
  
void* f2(__int64 i) {  
   return (void*)i;   // OK  
}  
```