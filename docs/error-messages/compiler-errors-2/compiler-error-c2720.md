---
title: Ошибка компилятора C2720 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2720
dev_langs:
- C++
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c6215cd2e83f1fa3a48c3cbd4970cd2d3466fc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233539"
---
# <a name="compiler-error-c2720"></a>Ошибка компилятора C2720  
  
> "*идентификатор*": "*описатель*" спецификатор класса хранения недопустим для членов  
  
Класс хранения нельзя использовать для членов класса вне объявления. Чтобы устранить эту ошибку, удалите ненужный [класс хранения](../../cpp/storage-classes-cpp.md) описатель из определения члена вне объявления класса.  
  
## <a name="example"></a>Пример  
  
В следующем примере показано возникновение ошибки C2720 и приводятся сведения по ее устранению.  
  
```cpp  
// C2720.cpp  
struct S {  
   static int i;  
};  
static S::i;   // C2720 - remove the unneeded 'static' to fix it  
```