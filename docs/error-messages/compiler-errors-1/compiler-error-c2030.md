---
title: "Ошибка компилятора C2030 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2030
dev_langs:
- C++
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c025fe57d411ae4744a10fe9bc062b336e189e83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2030"></a>Ошибка компилятора C2030
деструктор с модификатором доступа protected private не может быть членом класса, объявленного как sealed  
  
 Класс среды выполнения Windows, объявленный как `sealed`, не может содержать защищенный закрытый деструктор. Для запечатанных типов допустимы только открытые виртуальные и закрытые невиртуальные деструкторы. Дополнительные сведения см. в разделе [классы и структуры ссылки](../../cppcx/ref-classes-and-structs-c-cx.md).  
  
 Чтобы устранить эту ошибку, измените тип доступа деструктора.