---
title: Ошибка компилятора C2087 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2087
dev_langs:
- C++
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a6012bd49d9d68cbc3318afb390b5f5b411e39f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2087"></a>Ошибка компилятора C2087
«Идентификатор»: отсутствует индекс  
  
 В определении массива с несколькими индексами отсутствует значение индекса превышает единицу измерения.  
  
 Следующий пример приводит к возникновению ошибки C2087:  
  
```  
// C2087.cpp  
int main() {  
   char a[10][];   // C2087  
}  
```  
  
 Возможное решение  
  
```  
// C2087b.cpp  
int main() {  
   char b[4][5];  
}  
```