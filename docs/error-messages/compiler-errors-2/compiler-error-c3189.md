---
title: Ошибка компилятора C3189 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3189
dev_langs:
- C++
helpviewer_keywords:
- C3189
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acf0e49ecf9c8003d8dcfe035b14c8f5c5067dbc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3189"></a>Ошибка компилятора C3189
' typeid\<введите абстрактный декларатор > ": этот синтаксис больше не поддерживается, используйте:: typeid вместо  
  
 Устаревшая форма [typeid](../../windows/typeid-cpp-component-extensions.md) было использовать, используйте новую форму.  
  
 Следующий пример приводит к возникновению ошибки C3189:  
  
```  
// C3189.cpp  
// compile with: /clr  
int main() {  
   System::Type^ t  = typeid<System::Object>;   // C3189  
   System::Type^ t2  = System::Object::typeid;   // OK  
}  
```