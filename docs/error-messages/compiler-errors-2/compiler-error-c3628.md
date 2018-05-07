---
title: Ошибка компилятора C3628 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3628
dev_langs:
- C++
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5210a9bb91b86c63f0cebabce8901c9af50ae896
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3628"></a>Ошибка компилятора C3628
«базовый класс»: управляемый или WinRTclasses поддерживают только открытое наследование  
  
Была предпринята попытка использовать управляемый или WinRT классов как [закрытый](../../cpp/private-cpp.md) или [защищенных](../../cpp/protected-cpp.md) базового класса. Управляемый объект или класс WinRT может использоваться только как базовый класс с [открытый](../../cpp/public-cpp.md) доступа.  
  
В следующем примере показано возникновение ошибки C3628 и приводятся сведения по ее устранению.  
  
```  
// C3628a.cpp  
// compile with: /clr  
ref class B {  
};  
  
ref class D : private B {   // C3628  
  
// The following line resolves the error.  
// ref class D : public B {  
};  
  
int main() {  
}  
```  
