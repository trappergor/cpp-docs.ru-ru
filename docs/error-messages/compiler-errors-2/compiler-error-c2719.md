---
title: "Ошибка компилятора C2719 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2719
dev_langs:
- C++
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f7e6707dfd5666cb8852e3bbf59cf7a81dd24766
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2719"></a>Ошибка компилятора C2719
parameter: формальный параметр с __declspec(align('#')) не будет выровнен  
  
 [Выравнивание](../../cpp/align-cpp.md) `__declspec` модификатора не допускается в параметрах функций. Выравнивание параметров функции контролируется используемым соглашением о вызовах. Дополнительные сведения см. в разделе [соглашения о вызовах](../../cpp/calling-conventions.md).  
  
 В следующем примере показано возникновение ошибки C2719 и приводятся сведения по ее устранению.  
  
```  
// C2719.cpp  
void func(int __declspec(align(32)) i);   // C2719  
// try the following line instead  
// void func(int i);  
```
