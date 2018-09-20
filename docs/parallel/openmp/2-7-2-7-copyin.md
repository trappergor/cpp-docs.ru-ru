---
title: 2.7.2.7 copyin | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94b4c529b7ad6fd717be1e1dee0edd3ff9ac3ff5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426891"
---
# <a name="2727-copyin"></a>2.7.2.7 copyin

**Copyin** предложение предоставляет механизм для назначения то же значение для **threadprivate** переменные для каждого потока выполнения параллельной области группы. Для каждой переменной, указанной в **copyin** предложение, значение переменной в главный поток команды для копирования, как если назначение в частные для потока копии в начале параллельной области. Синтаксис **copyin** предложение выглядит следующим образом:

```

copyin(
variable-list
)

```

Ограничения, которые необходимо **copyin** предложение, следующим образом:

- Переменная, которая указана в **copyin** предложение необходимо иметь доступный и однозначный оператор присваивания копии.

- Переменная, которая указана в **copyin** предложение должно быть **threadprivate** переменной.