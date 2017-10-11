---
title: "Ошибка компилятора C3813 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3813
dev_langs:
- C++
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cabe753691b3d72ede25f0c25404d73fb63ceba8
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3813"></a>Ошибка компилятора C3813
объявление свойства должно находиться только в пределах определения управляемого типа или типа WinRT  
  
Объект [свойство](../../dotnet/how-to-use-properties-in-cpp-cli.md) можно объявлять только в пределах управляемого типа или среды выполнения Windows тип. Собственные типы не поддерживают ключевое слово `property`.  
  
## <a name="example"></a>Пример  
В следующем примере показано возникновение ошибки C3813 и приводятся сведения по ее устранению.  
  
```cpp  
// C3813.cpp  
// compile by using: cl /c /clr C3813.cpp  
class A  
{  
   property int Int; // C3813  
};  
  
ref class B  
{  
   property int Int; // OK - declared within managed type  
};  
```
