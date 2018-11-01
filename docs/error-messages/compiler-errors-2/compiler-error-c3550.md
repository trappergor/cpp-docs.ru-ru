---
title: Ошибка компилятора C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: dbed14b9f2fa0f2163484edd8b5dfa330af9cbf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498891"
---
# <a name="compiler-error-c3550"></a>Ошибка компилятора C3550

только неструктурированный описатель "decltype(auto)" разрешен в этом контексте

Если `decltype(auto)` используется как заполнитель для типа возвращаемого значения функции, он должен применяться сам по себе. Невозможно использовать его как часть объявления указателя (`decltype(auto*)`), объявления ссылки (`decltype(auto&)`) или любой другого подобного объявления.

## <a name="see-also"></a>См. также

[auto](../../cpp/auto-cpp.md)