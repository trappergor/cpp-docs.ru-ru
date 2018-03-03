---
title: "Ошибка компилятора C3071 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3071
dev_langs:
- C++
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dfe7bf24ac7b81387420a52cfb9f39989fe43b68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3071"></a>Ошибка компилятора C3071
оператор "operator" можно применить только к экземпляру класса ref или к типу значений  
  
 Оператор среды CLR нельзя использовать с неуправляемым типом. Оператор можно использовать в классе или структуре ссылки (тип значения), но не в управляемом типе, таком как int, или псевдониме управляемого типа, таком как System::Int32. Эти типы не могут быть упакованы в коде C++ так, чтобы они ссылались на управляемую переменную, поэтому оператор нельзя использовать.  
  
 Дополнительные сведения см. в разделе [оператор отслеживания ссылок](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3071.  
  
```  
// C3071.cpp  
// compile with: /clr  
class N {};  
ref struct R {};  
  
int main() {  
   N n;  
   %n;   // C3071  
  
   R r;  
   R ^ r2 = %r;   // OK  
}  
```