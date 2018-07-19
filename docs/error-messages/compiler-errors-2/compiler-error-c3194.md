---
title: Ошибка компилятора C3194 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3194
dev_langs:
- C++
helpviewer_keywords:
- C3194
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd6fad304dc4e400d6ca25c7e835b2d0a6935117
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247804"
---
# <a name="compiler-error-c3194"></a>Ошибка компилятора C3194
«член»: тип значения не может иметь оператор присваивания  
  
 Специальные функции-члены, требующие автоматической активации режима компилятором, такие как конструктор копии или оператором назначения копии не поддерживаются в классе значений.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3194.  
  
```  
// C3194.cpp  
// compile with: /clr /c  
value struct MyStruct {  
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194  
};  
  
ref struct MyStruct2 {  
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK  
};  
```