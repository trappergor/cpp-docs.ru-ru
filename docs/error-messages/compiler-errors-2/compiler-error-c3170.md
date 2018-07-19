---
title: Ошибка компилятора C3170 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3170
dev_langs:
- C++
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bb077bcad95de0be17e630803b5d4ea9825be61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33255917"
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