---
title: Ошибка компилятора C2719 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2719
dev_langs:
- C++
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee8779db363c506d2f4ad884e15f78ba8231caa7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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