---
title: Ошибка компилятора C3804 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3804
dev_langs:
- C++
helpviewer_keywords:
- C3804
ms.assetid: 7c4cda28-ec96-4d04-937b-36dbd9944722
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0bd4d5921037094b3050e7a3c003b507a9cae4c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267161"
---
# <a name="compiler-error-c3804"></a>Ошибка компилятора C3804
«метод_доступа_свойства»: методы доступа для свойства должны либо быть статическими, либо не статическими  
  
 При определении нетривиального свойства, функции доступа могут быть либо статическими или экземпляр, но не оба.  
  
 Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md) .  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3804.  
  
```  
// C3804.cpp  
// compile with: /c /clr  
ref struct A {  
  
   property int i {  
      static int get() {}  
      void set(int i) {}  
   }   // C3804 error  
  
   // OK  
   property int j {  
      int get() { return 0; }  
      void set(int i) {}  
   }  
  
   property int k {  
      static int get() { return 0; }  
      static void set(int i) {}  
   }  
};  
```