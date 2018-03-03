---
title: "Ошибка компилятора C2346 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2346
dev_langs:
- C++
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 769d5addc47ead8ffb338d5fbef313cd46735d31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2346"></a>Ошибка компилятора C2346
«функция» не может быть скомпилирована как управляемая: причина  
  
 Компилятору не удалось скомпилировать функцию на языке MSIL.  
  
 Дополнительные сведения см. в разделе [управляемые, неуправляемые](../../preprocessor/managed-unmanaged.md) и [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Удалите этот код в функцию, которую нельзя скомпилировать в MSIL-код.  
  
2.  Либо не компилируйте модуль с **/CLR**, либо пометьте функцию как неуправляемую с неуправляемая прагма.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2346.  
  
```  
// C2346.cpp  
// processor: x86  
// compile with: /clr   
// C2346 expected  
struct S  
{  
   S()  
   {  
      { __asm { nop } }  
   }  
   virtual __clrcall ~S() { }  
};  
  
void main()  
{  
   S s;  
}  
```