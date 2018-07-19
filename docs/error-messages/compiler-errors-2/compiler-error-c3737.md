---
title: Ошибка компилятора C3737 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3737
dev_langs:
- C++
helpviewer_keywords:
- C3737
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29d31597e9581d03f97c2b07856ce81c5de50bd3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264614"
---
# <a name="compiler-error-c3737"></a>Ошибка компилятора C3737
«делегат»: делегат не может иметь явное соглашение о вызовах  
  
 Нельзя указать [соглашение о вызовах](../../cpp/calling-conventions.md) для `delegate`.  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C3737:  
  
```  
// C3737a.cpp  
// compile with: /clr  
delegate void __stdcall MyFunc();   // C3737  
// Try the following line instead.  
// delegate void MyFunc();  
  
int main() {  
}  
```  
