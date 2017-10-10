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
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bf0133aba65b8477bd949cd90b51edbd407bcda7
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
