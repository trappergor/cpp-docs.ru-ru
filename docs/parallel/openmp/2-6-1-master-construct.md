---
title: 2.6.1 Конструкция master
ms.date: 11/04/2016
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
ms.openlocfilehash: 0501b1fdfbd36829cee2793fc0f7bb03daeda900
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475534"
---
# <a name="261-master-construct"></a>2.6.1 Конструкция master

**Master** директива определяет конструкцию, которая указывает структурированный блок, который выполняется потоком главной рабочей группы. Синтаксис **master** директива выглядит следующим образом:

```
#pragma omp master new-linestructured-block
```

Другие потоки в группе не выполняйте структурированных блоку. Нет преград подразумеваемых на запись или выход из конструкция master.