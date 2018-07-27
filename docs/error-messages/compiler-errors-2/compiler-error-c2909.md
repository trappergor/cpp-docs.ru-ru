---
title: Ошибка компилятора C2909 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2909
dev_langs:
- C++
helpviewer_keywords:
- C2909
ms.assetid: 1c9df8ae-925d-4002-a5f8-a71413c45f9e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9bb5252c0122f5610348c5fb154fedd1869d131e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245446"
---
# <a name="compiler-error-c2909"></a>Ошибка компилятора C2909
"идентификатор": для явного создания экземпляра шаблона функции требуется тип возврата  
  
 Для явного создания экземпляра шаблона функции требуется явное указание его типа возврата. Неявная спецификация типа возврата не работает.  
  
 В следующем примере возникает ошибка C2909:  
  
```  
// C2909.cpp  
// compile with: /c  
template<class T> int f(T);  
template f<int>(int);         // C2909  
template int f<int>(int);   // OK  
```