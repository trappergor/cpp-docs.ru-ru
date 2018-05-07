---
title: Ошибка компилятора C2150 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2150
dev_langs:
- C++
helpviewer_keywords:
- C2150
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7dc7a84ff666fdc17f0abeec690a548f216ce975
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2150"></a>Ошибка компилятора C2150
  
> "*идентификатор*": битовое поле должно иметь тип «int», «signed int» или «unsigned int»  
  
 Базовый тип для битового поля должен быть `int`, `signed int`, или `unsigned int`.  
  
## <a name="example"></a>Пример  
  
 В этом примере показано, как можно столкнуться C2150 и способах ее устранения:  
  
```cpp  
// C2150.cpp  
// compile with: /c  
struct A {  
   float a : 8;    // C2150  
   int i : 8;      // OK  
};  
```