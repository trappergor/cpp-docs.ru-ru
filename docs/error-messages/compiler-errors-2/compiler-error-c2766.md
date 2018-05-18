---
title: Ошибка компилятора C2766 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2766
dev_langs:
- C++
helpviewer_keywords:
- C2766
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0cd83bc18e30fb9b183e27597b1c5902f734c88a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2766"></a>Ошибка компилятора C2766
явная специализация; «специализация» уже определен  
  
 Дублирование явной специализации не допускаются. Дополнительные сведения см. в разделе [явной специализации шаблонов функций](../../cpp/explicit-specialization-of-function-templates.md).  
  
 Следующий пример приводит к возникновению ошибки C2766:  
  
```  
// C2766.cpp  
// compile with: /c  
template<class T>   
struct A {};  
  
template<>   
struct A<int> {};  
  
template<>   
struct A<int> {};   // C2766  
// try the following line instead  
// struct A<char> {};  
```