---
title: Ошибка компилятора C3296 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3296
dev_langs:
- C++
helpviewer_keywords:
- C3296
ms.assetid: fc4c9dcd-16cf-4eee-a1ac-c43e7c29e443
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85b4f80a9f257fa5e5d9ed8701a6ee7cfdf68cfd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249971"
---
# <a name="compiler-error-c3296"></a>Ошибка компилятора C3296
"свойство": свойство с таким именем уже существует  
  
 Компилятор обнаружил несколько свойств с одинаковым именем. Каждое свойство в типе должно иметь уникальное имя.  
  
 Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3296:  
  
```  
// C3296.cpp  
// compile with: /clr /c  
using namespace System;  
  
ref class R {  
public:  
   property int MyProp[int] { int get(int); }  
  
   property String^ MyProp[int] { void set(int, String^); }   // C3296  
};  
```