---
title: Ошибка компилятора C2585 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ab812a4b6621acb28a4df636056598047f5c21e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230165"
---
# <a name="compiler-error-c2585"></a>Ошибка компилятора C2585
явное преобразование в «тип» является неоднозначным  
  
 Преобразование типов может иметь несколько результатов.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Преобразование из типа класса или структуры на основе множественного наследования. Если тип наследует более одного раза для одного базового класса, функция или оператор преобразования должны использовать разрешение области (`::`) чтобы указать, какие из этих классов для использования при преобразовании.  
  
2.  Оператор преобразования и конструктор определено сделать то же самое преобразование.