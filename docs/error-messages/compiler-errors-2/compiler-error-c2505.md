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
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: cd11a76d1cbfd6f082c4926816a99c29733994c3
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2505"></a>Ошибка компилятора C2505
«символ»: параметр «__declspec(модификатор)» может применяться только в объявлениях или определениях глобальных объектов или статических данных-членов  
  
 A `__declspec` модификатор, который предназначен для использования только в глобальной области был использован в функции.  
  
 Дополнительные сведения см. в разделе [appdomain](../../cpp/appdomain.md) и [процесс](../../cpp/process.md).  
  
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
