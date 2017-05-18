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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c27182ee0c2648fb6d3e6579ed78858119de3f9f
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2719"></a>Ошибка компилятора C2719
parameter: формальный параметр с __declspec(align('#')) не будет выровнен  
  
 [Выравнивания](../../cpp/align-cpp.md) `__declspec` модификатор с параметрами функций не допускается. Выравнивание параметров функции контролируется используемым соглашением о вызовах. Дополнительные сведения см. в разделе [соглашения о вызовах](../../cpp/calling-conventions.md).  
  
 В следующем примере показано возникновение ошибки C2719 и приводятся сведения по ее устранению.  
  
```  
// C2719.cpp  
void func(int __declspec(align(32)) i);   // C2719  
// try the following line instead  
// void func(int i);  
```
