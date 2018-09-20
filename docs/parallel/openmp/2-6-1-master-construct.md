---
title: 2.6.1 конструкция-шаблоны | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d82ae673e428c635172f35f9b0f682aa65dc2b8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445637"
---
# <a name="261-master-construct"></a>2.6.1 Конструкция master

**Master** директива определяет конструкцию, которая указывает структурированный блок, который выполняется потоком главной рабочей группы. Синтаксис **master** директива выглядит следующим образом:

```
#pragma omp master new-linestructured-block
```

Другие потоки в группе не выполняйте структурированных блоку. Нет преград подразумеваемых на запись или выход из конструкция master.