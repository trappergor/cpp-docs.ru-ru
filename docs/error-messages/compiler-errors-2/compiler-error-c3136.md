---
title: Ошибка компилятора C3136 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3136
dev_langs:
- C++
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f892c7f3d1ca7bf2aebf3ecfe7574182b544fd01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248855"
---
# <a name="compiler-error-c3136"></a>Ошибка компилятора C3136
«интерфейс»: интерфейс COM может наследовать только от другого интерфейса COM, «интерфейс» не является COM-интерфейс  
  
 Интерфейс, к которому применен [атрибут интерфейса](../../windows/interface-attributes.md) наследует от интерфейса, который не является COM-интерфейса. COM-интерфейс наследует от `IUnknown`. Любой интерфейс предшествует атрибут интерфейса является COM-интерфейса.  
  
 Следующий пример приводит к возникновению ошибки C3136:  
  
```  
// C3136.cpp  
#include "unknwn.h"  
  
__interface A   // C3136  
// try the following line instead  
// _interface A : IUnknown  
{  
   int a();  
};  
  
[object]  
__interface B : A  
{  
   int aa();  
};  
```