---
title: Ошибка компилятора C2506 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2506
dev_langs:
- C++
helpviewer_keywords:
- C2506
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5369a6a5bf904f7a7492037fbad4df44de92e66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228522"
---
# <a name="compiler-error-c2506"></a>Ошибка компилятора C2506
«член»: «__declspec(модификатор)» не может применяться к этому символу  
  
 Для статических членов управляемого класса нельзя объявлять на уровне процесса или на уровне домена приложения.  
  
 Дополнительные сведения см. в разделе [appdomain](../../cpp/appdomain.md) .  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2506.  
  
```  
// C2506.cpp  
// compile with: /clr /c  
ref struct R {  
   __declspec(process) static int n;   // C2506  
   int o;   // OK  
};  
```