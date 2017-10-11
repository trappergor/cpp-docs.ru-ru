---
title: "Ошибка компилятора C3170 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3170
dev_langs:
- C++
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: aa11ac93ab7e5637153a063a892d99e127b80f54
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3170"></a>Ошибка компилятора C3170
не могут иметь разных идентификаторов модулей в проекте  
  
 [модуль](../../windows/module-cpp.md) в двух файлах при компиляции были обнаружены атрибуты с разными именами. Только один уникальный `module` атрибут можно задать на каждую компиляцию.  
  
 Идентичные `module` атрибуты могут быть заданы в более чем один файл исходного кода.  
  
 Например, если найдены следующие атрибуты модуля:  
  
```  
// C3170.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
int main() {}  
```  
  
 Затем:  
  
```  
// C3170b.cpp  
// compile with: C3170.cpp  
// C3170 expected  
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
```  
  
 компилятор выдаст ошибку C3170 (Обратите внимание, разные имена).
