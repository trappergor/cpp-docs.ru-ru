---
title: "Ошибка компилятора C3012 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3012
dev_langs: C++
helpviewer_keywords: C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a75b8845fafef81768ae5a2da8c81e8734db4ebf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3012"></a>Ошибка компилятора C3012
  
> "*встроенная функция*": подставляемая функция непосредственно внутри параллельной области не допускается  
  
 Объект [встроенные функции компилятора](../../intrinsics/compiler-intrinsics.md) функции не допускается в `omp parallel` области. Чтобы устранить эту проблему, переместите встроенные объекты из области или замените невстроенный эквиваленты.   
  
## <a name="example"></a>Пример  
  
 Следующий пример приводит к возникновению ошибки C3012 и показано, как исправить эту ошибку:  
  
```cpp  
// C3012.cpp  
// compile with: /openmp  
#ifdef __cplusplus  
extern "C" {  
#endif  
void* _ReturnAddress();  
#ifdef __cplusplus  
}  
#endif  
  
int main()  
{  
   #pragma omp parallel  
   {  
      _ReturnAddress();   // C3012  
   }  
   _ReturnAddress();      // OK  
}  
```