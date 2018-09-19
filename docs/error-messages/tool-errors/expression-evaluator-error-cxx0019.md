---
title: Ошибка вычислителя выражений CXX0019 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0019
dev_langs:
- C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3fba76b75c640917b3b99cd41500d682cb1b32f0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031812"
---
# <a name="expression-evaluator-error-cxx0019"></a>Ошибка вычислителя выражений CXX0019

Неверный тип приведения

Вычислитель выражений C не удается выполнить приведение типа согласно записи.

Эта ошибка идентична ошибке CAN0019.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Указанный тип неизвестен.

1. Было слишком много уровней типов указателей. Например приведение типа

    ```
    (char **)h_message
    ```

     Невозможно вычислить с помощью вычислителя выражений C.