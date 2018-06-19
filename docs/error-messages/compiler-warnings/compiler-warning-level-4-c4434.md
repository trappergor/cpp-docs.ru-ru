---
title: Предупреждение компилятора (уровень 4) C4434 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4434
dev_langs:
- C++
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c639fa1cc89266fd9cc2935d88132ceae225a85e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293417"
---
# <a name="compiler-warning-level-4-c4434"></a>Предупреждение компилятора (уровень 4) C4434
конструктор класса должен быть закрытым; закрытый доступ  
  
 C4434 указывает, что компилятор изменил доступность статический конструктор. Статические конструкторы должны быть закрытыми, как они предназначены только для вызывается средой CLR. Дополнительные сведения см. в разделе [статические конструкторы](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4434.  
  
```  
// C4434.cpp  
// compile with: /W4 /c /clr  
public ref struct R {  
   static R(){}   // C4434  
};  
```