---
title: "Ошибка компилятора C2505 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2505
dev_langs:
- C++
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 05ada08fa7c85f7d67829bceab1bd9a4c4f67fdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2505"></a>Ошибка компилятора C2505
«символ»: параметр «__declspec(модификатор)» может применяться только в объявлениях или определениях глобальных объектов или статических элементов данных  
  
 Объект `__declspec` модификатор, который должен использоваться только в глобальной области видимости был использован в функции.  
  
 Дополнительные сведения см. в разделах [appdomain](../../cpp/appdomain.md) и [process](../../cpp/process.md).  
  
 Следующий пример приводит к возникновению ошибки C2505:  
  
```  
// C2505.cpp  
// compile with: /clr  
  
// OK  
__declspec(process) int ii;  
__declspec(appdomain) int jj;  
  
int main() {  
   __declspec(process) int i;   // C2505  
   __declspec(appdomain) int j;   // C2505  
}  
```