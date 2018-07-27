---
title: Ошибка компилятора C3865 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3865
dev_langs:
- C++
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99a872d4cf7ed285a0798461c77adf904cfa3e71
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275503"
---
# <a name="compiler-error-c3865"></a>Ошибка компилятора C3865
«соглашение_о_вызовах»: может использоваться только в собственных функциях-членах  
  
 Соглашение о вызовах использовался на функцию, которая была глобальной функции или функции-члена управляемого. Соглашение о вызовах может использоваться только в функции-члене native (неуправляемой).  
  
 Дополнительные сведения см. в разделе [соглашения о вызовах](../../cpp/calling-conventions.md).  
  
 Следующий пример приводит к возникновению ошибки C3865:  
  
```  
// C3865.cpp  
// compile with: /clr  
// processor: x86  
void __thiscall Func(){}   // C3865  
  
// OK  
struct MyType {  
   void __thiscall Func(){}  
};  
```