---
title: "Ошибка компилятора C2344 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2344
dev_langs:
- C++
helpviewer_keywords:
- C2344
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c7044ae9c2e15caa7ea2e0992512d22a146ec22a
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2344"></a>Ошибка компилятора C2344
align(#): выравнивание должно быть степенью двух  
  
 При использовании ключевого слова [align](../../cpp/align-cpp.md) передаваемое значение должно быть степенью двух.  
  
 Например, приведенный ниже код вызывает ошибку C2344, так как число 3 не является степенью двух.  
  
```  
// C2344.cpp  
// compile with: /c  
__declspec(align(3)) int a;   // C2344  
__declspec(align(4)) int b;   // OK  
```
