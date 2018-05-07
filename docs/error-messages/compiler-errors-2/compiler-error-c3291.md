---
title: Ошибка компилятора C3291 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3291
dev_langs:
- C++
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 829479ce2514d77f5be99feae03edf056963af7c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3291"></a>Ошибка компилятора C3291
default: не может быть именем тривиального свойства  
  
 Тривиальное свойство нельзя назвать `default` Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md) .  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3291.  
  
```  
// C3291.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String ^ default;   // C3291  
   property System::String ^ Default;   // OK  
};  
```