---
title: Ошибка компилятора C3171 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3171
dev_langs:
- C++
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ee6ee02511242e2af87024c741a3c97f3f3724d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3171"></a>Ошибка компилятора C3171
«module»: невозможно указать другие атрибуты модуля в проекте  
  
 [модуль](../../windows/module-cpp.md) атрибуты с различными списками параметров были найдены в двух файлах при компиляции. Только один уникальный `module` атрибут можно задать на каждую компиляцию.  
  
 Идентичные `module` атрибуты могут быть заданы в более чем один файл исходного кода.  
  
 Например если следующие `module` обнаружены атрибуты:  
  
```  
// C3171.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];  
int main() {}  
```  
  
 Затем:  
  
```  
// C3171b.cpp  
// compile with: C3171.cpp  
// C3171 expected  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];  
```  
  
 компилятор создаст C3171 (запишите значения разных версий).