---
title: Ошибка компилятора C2346 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2346
dev_langs:
- C++
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9459d7330738180e92776e93fcba9a07bfd39640
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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