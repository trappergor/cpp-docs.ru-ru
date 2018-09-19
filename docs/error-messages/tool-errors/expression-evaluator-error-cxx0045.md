---
title: Ошибка вычислителя выражений CXX0045 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0045
dev_langs:
- C++
helpviewer_keywords:
- CXX0045
- CAN0045
ms.assetid: 32181bc8-e79c-4ad7-a82f-47c62ec06d7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d9913bc77dfc3fbc95bd03fd32c954c4d304d27
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023206"
---
# <a name="expression-evaluator-error-cxx0045"></a>Ошибка вычислителя выражений CXX0045

не является функцией

Список аргументов был назначен для символа в программе, которая не является именем функции.

## <a name="example"></a>Пример

```
queue( alpha, beta )
```

Когда `queue` не является функцией.

Эта ошибка идентична ошибке CAN0045.