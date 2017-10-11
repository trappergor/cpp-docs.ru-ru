---
title: "Ошибка компилятора C2665 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2665
dev_langs:
- C++
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5a349df2c60d746b6b090953362c7c6801e1f2a3
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

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
