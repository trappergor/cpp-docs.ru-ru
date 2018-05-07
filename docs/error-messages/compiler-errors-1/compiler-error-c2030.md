---
title: Ошибка компилятора C2030 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2030
dev_langs:
- C++
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ceccc1088e32382167e7e6400360b30de07fde1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2030"></a>Ошибка компилятора C2030
деструктор с модификатором доступа protected private не может быть членом класса, объявленного как sealed  
  
 Класс среды выполнения Windows, объявленный как `sealed`, не может содержать защищенный закрытый деструктор. Для запечатанных типов допустимы только открытые виртуальные и закрытые невиртуальные деструкторы. Дополнительные сведения см. в разделе [классы и структуры ссылки](../../cppcx/ref-classes-and-structs-c-cx.md).  
  
 Чтобы устранить эту ошибку, измените тип доступа деструктора.