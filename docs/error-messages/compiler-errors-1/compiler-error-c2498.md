---
title: Ошибка компилятора C2498 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2498
dev_langs:
- C++
helpviewer_keywords:
- C2498
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c50596e4e5ca47a0f1bdf3f5ab25405139b66447
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196614"
---
# <a name="compiler-error-c2498"></a>Ошибка компилятора C2498
«функция»: «novtable» может применяться только к объявлениям или определениям классов  
  
 Эта ошибка может вызываться с помощью `__declspec(novtable)` с функцией.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2498:  
  
```  
// C2498.cpp  
// compile with: /c  
void __declspec(novtable) f() {}   // C2498  
class __declspec(novtable) A {};   // OK  
```