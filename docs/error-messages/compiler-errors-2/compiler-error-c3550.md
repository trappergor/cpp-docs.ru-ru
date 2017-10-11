---
title: "Ошибка компилятора C3550 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3550
dev_langs:
- C++
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 52b3e3323bac9ad55ff10481b3504e4e054ba874
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3550"></a>Ошибка компилятора C3550
только неструктурированный описатель "decltype(auto)" разрешен в этом контексте  
  
 Если `decltype(auto)` используется как заполнитель для возвращаемого типа функции, он должен применяться сам по себе. Невозможно использовать его как часть объявления указателя (`decltype(auto*)`), объявления ссылки (`decltype(auto&)`) или любой другого подобного объявления.  
  
## <a name="see-also"></a>См. также  
 [auto](../../cpp/auto-cpp.md)
