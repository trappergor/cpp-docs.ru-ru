---
title: Ошибка компилятора C2665 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2665
dev_langs:
- C++
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18cc99d6ea0a45e7c096a13cfe57dc841ca351bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2665"></a>Ошибка компилятора C2665
«функция»: ни одна из перегрузок Число1 число2 параметра может выполнить преобразование из типа «тип»  
  
 Параметр перегруженной функции не может быть преобразован в требуемый тип.  Возможные решения:  
  
-   Укажите оператор преобразования.  
  
-   Используйте явное преобразование.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2665.  
  
```  
// C2665.cpp  
void func(short, char*){}  
void func(char*, char*){}  
  
int main() {  
   func(0, 1);   // C2665  
   func((short)0, (char*)1);   // OK  
}  
```