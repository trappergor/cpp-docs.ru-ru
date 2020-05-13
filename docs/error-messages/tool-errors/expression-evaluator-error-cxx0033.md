---
title: Ошибка вычислителя выражений CXX0033
ms.date: 11/04/2016
f1_keywords:
- CXX0033
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
ms.openlocfilehash: 2916808d98f1fabc2157fbedc96d76e196661279
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195517"
---
# <a name="expression-evaluator-error-cxx0033"></a>Ошибка вычислителя выражений CXX0033

Ошибка в сведениях о типе OMF

Исполняемый файл не имеет допустимого формата объекта (OMF) для отладки.

Эта ошибка идентична CAN0033.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Исполняемый файл не был создан с помощью компоновщика, выпущенного в этой версии C++Visual. Повторно свяжите объектный код с помощью текущей версии LINK. exe.

1. Возможно, файл exe поврежден. Перекомпилируйте и повторно свяжите программу.
