---
title: "Хранение объединений | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- storage, union
- union keyword [C], storage
- union keyword [C]
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cb349b2c1649b6e4e46fcc92829de87043d0c50a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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