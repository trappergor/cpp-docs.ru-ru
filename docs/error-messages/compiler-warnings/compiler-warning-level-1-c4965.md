---
title: "Предупреждение (уровень 1) C4965 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4965
dev_langs:
- C++
helpviewer_keywords:
- C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
caps.latest.revision: 14
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 53ed24bf928a971d1a315af73fa01b786da8958e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4965"></a>Предупреждение компилятора (уровень 1) C4965
неявная упаковка целого числа 0; используйте nullptr или явное приведение типов  
  
 Visual C++ поддерживает неявная упаковка-преобразование типов значений. Инструкция, которая привела к нулевому назначению с помощью управляемых расширений для C++ теперь становится назначением с упакованным  
  
 Дополнительные сведения см. в разделе [упаковки](../../windows/boxing-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4965.  
  
```  
// C4965.cpp  
// compile with: /clr /W1  
int main() {  
   System::Object ^o = 0;   // C4965  
  
   // the previous line is the same as the following line  
   // using Managed Extensions for C++  
   // System::Object *o = __box(0);  
  
   // OK  
   System::Object ^o2 = nullptr;  
   System::Object ^o3 = safe_cast<System::Object^>(0);  
}  
```
