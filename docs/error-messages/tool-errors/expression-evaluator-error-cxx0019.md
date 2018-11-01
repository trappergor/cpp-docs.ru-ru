---
title: Ошибка вычислителя выражений CXX0019
ms.date: 11/04/2016
f1_keywords:
- CXX0019
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
ms.openlocfilehash: 266e97f28cf0f27cb87e9743399c66aba87c0e8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658098"
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