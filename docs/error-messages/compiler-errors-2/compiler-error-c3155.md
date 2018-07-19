---
title: Ошибка компилятора C3155 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3155
dev_langs:
- C++
helpviewer_keywords:
- C3155
ms.assetid: b04a42e1-64e7-40f8-81fe-c7945348b2cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 383727d6f1665544654c047f37f094a38d6b5309
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249818"
---
# <a name="compiler-error-c3155"></a>Ошибка компилятора C3155
атрибуты не допускаются в индексаторе свойства  
  
Индексированное свойство объявлено неправильно. Дополнительные сведения см. в разделе [как: используйте свойства в C + +/ CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C3155.  
  
```  
// C3155.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct R {  
   property int F[[ParamArray] int] {   // C3155  
   // try the following line instead  
   // property int F[ int] {   // OK  
      int get(int i) {   
         return 0;   
      }  
   }  
};  
```