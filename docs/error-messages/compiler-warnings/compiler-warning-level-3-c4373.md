---
title: "Предупреждение (уровень 3) C4373 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4373
dev_langs:
- C++
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 36d4491f8a621f1ee97de9682faf94a26a89fa70
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4373"></a>Предупреждение компилятора (уровень 3) C4373
%$S: виртуальная функция переопределяет "%$pS", предыдущие версии компилятора не выполняли переопределение, когда параметры отличались только квалификаторами const или volatile  
  
 Приложение содержит метод в производном классе, который переопределяет виртуальный метод в базовом классе, и параметры в переопределяющем методе отличаются только [const](../../cpp/const-cpp.md) или [volatile](../../cpp/volatile-cpp.md) квалификатор от параметров виртуального метода. Это означает, что компилятор должен привязать ссылку на функцию к методу в базовом или производном классе.  
  
 Версии компилятора до [!INCLUDE[cpp_orcas_long](../../cpp/includes/cpp_orcas_long_md.md)] привязывают функцию к методу в базовом классе, а затем выдают предупреждение. Последующие версии компилятора игнорируют квалификатор `const` или `volatile` , привязывают функцию к методу в производном классе, а затем выдают предупреждение `C4373`. Поведение в последнем случае соответствует стандарту C++.  
  
## <a name="example"></a>Пример  
 Следующий пример кода приводит к возникновению ошибки C4373.  
  
```  
// c4373.cpp  
// compile with: /c /W3  
#include <stdio.h>  
struct Base  
{  
    virtual void f(int i) {  
        printf("base\n");  
    }  
};  
struct Derived : Base  
{  
    void f(const int i) {  // C4373  
        printf("derived\n");  
    }  
};  
void main()  
{  
    Derived d;  
    Base* p = &d;  
    p->f(1);  
}  
```  
  
```Output  
derived  
```
