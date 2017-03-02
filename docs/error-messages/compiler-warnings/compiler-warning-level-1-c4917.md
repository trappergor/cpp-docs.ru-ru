---
title: "Предупреждение (уровень 1) C4917 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4917
dev_langs:
- C++
helpviewer_keywords:
- C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: 43dce460fb336b09ce39d3e4c0e52b43a175ea36
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4917"></a>Предупреждение компилятора (уровень 1) C4917
«декларатор»: идентификатор GUID может связываться только с классом, интерфейсом или пространства имен  
  
Пользовательские структуры, отличных от [класса](../../cpp/class-cpp.md), [интерфейс](../../cpp/interface.md), или [имен](../../cpp/namespaces-cpp.md) не могут иметь идентификатор GUID.  
  
Это предупреждение отключено по умолчанию. В разделе [компилятора предупреждения, — это отключение по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md) подробнее.  
  
## <a name="example"></a>Пример  
Следующий пример кода создает C4917:  
  
```cpp  
// C4917.cpp  
// compile with: /W1  
#pragma warning(default : 4917)  
__declspec(uuid("00000000-0000-0000-0000-000000000001")) struct S  
{  
} s;   // C4917, don't put uuid on a struct  
  
int main()  
{  
}  
```
