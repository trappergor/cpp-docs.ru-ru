---
title: Ошибка компилятора C3106 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3106
dev_langs:
- C++
helpviewer_keywords:
- C3106
ms.assetid: 39d97a32-0905-4702-87d3-7f8ce473fb93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 059eaf684995dab6bdcbd1a65bbdb75f70b1551b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248151"
---
# <a name="compiler-error-c3106"></a>Ошибка компилятора C3106
«атрибут»: неименованные аргументы должны предшествовать именованные аргументы  
  
 Неименованные аргументы должны передаваться атрибуту перед именованными аргументами.  
  
 Дополнительные сведения см. в разделе [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3106.  
  
```  
// C3106.cpp  
// compile with: /c  
[module(name="MyLib", dll)];   // C3106  
[module(dll, name="MyLib")];   // OK  
```