---
title: Предупреждение компилятора C4972 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4972
dev_langs:
- C++
helpviewer_keywords:
- C4972
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf5337a60781c6fb39281f051657ea7ebd9371fa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270955"
---
# <a name="compiler-warning-c4972"></a>Предупреждение компилятора C4972
Прямое изменение или обработка результатов операции распаковки в виде левостороннего значения недоступны для проверки  
  
 Разыменование дескриптора до типа значения, также называемое распаковкой, а затем присвоение ему значения не проверяется.  
  
 Дополнительные сведения см. в разделе [упаковка-преобразование](../../windows/boxing-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению предупреждения C4972:  
  
```  
// C4972.cpp  
// compile with: /clr:safe  
using namespace System;  
ref struct R {  
   int ^ p;   // a value type  
};  
  
int main() {  
   R ^ r = gcnew R;  
   *(r->p) = 10;   // C4972  
  
   // OK  
   r->p = 10;  
   Console::WriteLine( r->p );  
   Console::WriteLine( *(r->p) );  
}  
```