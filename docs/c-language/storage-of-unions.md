---
title: "Хранение объединений | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- storage, union
- union keyword [C], storage
- union keyword [C]
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: daea5794708456fad8b8ff2b3bb5900ec8df7264
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

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
