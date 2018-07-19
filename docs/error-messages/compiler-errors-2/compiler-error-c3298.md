---
title: Ошибка компилятора C3298 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3298
dev_langs:
- C++
helpviewer_keywords:
- C3298
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a67e155fb6cf0eab1ea085839d075d4d835de101
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250880"
---
# <a name="compiler-error-c3298"></a>Ошибка компилятора C3298
"ограничение_1": невозможно использовать "ограничение_2" как ограничение, поскольку "ограничение_2" имеет ограничение ссылки, а "ограничение_1" имеет ограничение значения  
  
 Нельзя указывать взаимно исключающие характеристики для ограничения. Например, параметр универсального типа не может быть ограничен одновременно типом значения и ссылочным типом.  
  
 Дополнительные сведения см. в разделе [ограничений для параметров универсального типа (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3298.  
  
```  
// C3298.cpp  
// compile with: /clr /c   
generic<class T, class U>  
where T : ref class  
where U : T, value class   // C3298  
public ref struct R {};  
```