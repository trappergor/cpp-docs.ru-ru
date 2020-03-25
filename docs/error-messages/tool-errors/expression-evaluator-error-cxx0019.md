---
title: Ошибка вычислителя выражений CXX0019
ms.date: 11/04/2016
f1_keywords:
- CXX0019
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
ms.openlocfilehash: 61646462eeba4918a4993b23f7f4b394083296ce
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195894"
---
# <a name="expression-evaluator-error-cxx0019"></a>Ошибка вычислителя выражений CXX0019

неверное приведение типа

Вычислителю выражений C не удается выполнить приведение типа, как записано.

Эта ошибка идентична CAN0019.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Указанный тип неизвестен.

1. Слишком много уровней типов указателей. Например, приведенный тип

    ```
    (char **)h_message
    ```

   не может вычисляться средством оценки выражений C.
