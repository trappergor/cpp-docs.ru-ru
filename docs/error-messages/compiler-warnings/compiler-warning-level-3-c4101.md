---
title: Предупреждение (уровень 3) C4101 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4101
dev_langs:
- C++
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 973b966e4b589cb35ffc92da9031779b14d448e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4101"></a>Предупреждение (уровень 3) C4101 компилятора
«Идентификатор»: неиспользованная локальная переменная  
  
 Локальная переменная никогда не используется. Это предупреждение возникает в очевидной ситуации:  
  
```  
// C4101a.cpp  
// compile with: /W3  
int main() {  
int i;   // C4101  
}  
```  
  
 Однако это предупреждение также может возникнуть при вызове **статических** функции-члена через экземпляр класса:  
  
```  
// C4101b.cpp  
// compile with:  /W3  
struct S {  
   static int func()  
   {  
      return 1;  
   }  
};  
  
int main() {  
   S si;   // C4101, si is never used  
   int y = si.func();  
   return y;  
}  
```  
  
 В этом случае компилятор использует сведения о `si` для доступа к **статических** функция, а экземпляр класса не требуется для вызова **статических** функции; таким образом предупреждение. Чтобы устранить это предупреждение, можно выполнить следующее.  
  
-   Добавьте конструктор, в котором компилятор будет использовать экземпляр `si` в вызове `func`.  
  
-   Удалить **статических** ключевое слово из определения `func`.  
  
-   Вызовите **статических** функции явно: `int y = S::func();`.