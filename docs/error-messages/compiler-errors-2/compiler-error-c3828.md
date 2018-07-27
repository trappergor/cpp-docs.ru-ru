---
title: Ошибка компилятора C3828 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3828
dev_langs:
- C++
helpviewer_keywords:
- C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adb016c164923e1ac6008e6318e39f8ac8632113
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267424"
---
# <a name="compiler-error-c3828"></a>Ошибка компилятора C3828
«Тип объекта»: аргументы размещения не разрешаются при создании экземпляров управляемых классов и WinRTclasses  
  
 При создании объекта управляемого типа или типа среды выполнения Windows, нельзя использовать формы размещения оператора [ref new gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md) или [новый](../../cpp/new-operator-cpp.md).  
  
 В следующем примере показано возникновение ошибки C3828 и приводятся сведения по ее устранению.  
  
```  
// C3828a.cpp  
// compile with: /clr  
ref struct M {  
};  
  
ref struct N {  
   static array<char>^ bytes = gcnew array<char>(256);  
};  
  
int main() {  
   M ^m1 = new (&N::bytes) M();   // C3828  
   // The following line fixes the error.  
   // M ^m1 = gcnew M();  
}  
```