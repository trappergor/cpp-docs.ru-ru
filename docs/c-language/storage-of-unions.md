---
title: Хранение объединений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- storage, union
- union keyword [C], storage
- union keyword [C]
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a741444aa9b0e9af1e1eb344a8ac7029127af3f9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386571"
---
# <a name="storage-of-unions"></a>Хранение объединений
Хранилище, связанное с переменной объединения, — это хранилище, необходимое для наибольшего члена объединения. При хранении наименьшего члена переменная объединения может содержать неиспользуемую область памяти. Все члены хранятся в одной области памяти и начинаются с одного и того же адреса. Сохраненное значение перезаписывается каждый раз, когда значение присваивается другому члену. Пример:  
  
```  
union         /* Defines a union named x */  
{  
    char *a, b;  
    float f[20];  
} x;  
```  
  
 Члены объединения `x` являются (в порядке их объявления) указателями на значение `char`, значение `char` и массив значений **float**. Хранилище, выделенное для `x`, — это хранилище, необходимое для массива `f`, состоящего из 20 элементов, поскольку `f` является самым длинным членом объединения. Так как ни один тег не связан с объединением, его тип является безымянным или анонимным.  
  
## <a name="see-also"></a>См. также  
 [Объявления объединений](../c-language/union-declarations.md)