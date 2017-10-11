---
title: "Ошибка компилятора C3320 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3320
dev_langs:
- C++
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fbc375682bb42070d49dd08b711926462c17f32b
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3320"></a>Ошибка компилятора C3320
"тип": имя типа не может совпадать со свойством name модуля  
  
Экспортированный определяемых пользователем типов (UDT), который может быть структуры, класса, перечисления или объединения, не может иметь то же имя, как параметр, передаваемый в [модуль](../../windows/module-cpp.md) свойство имени атрибута.  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C3320:  
  
```cpp  
// C3320.cpp  
#include "unknwn.h"  
[module(name="xx")];  
  
[export] struct xx {   // C3320  
// Try the following line instead  
// [export] struct yy {  
   int i;  
};  
```
