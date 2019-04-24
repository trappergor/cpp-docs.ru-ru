---
title: Ошибка компилятора C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: 106ac93496eebb25ee603251d84680053e1310b7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032341"
---
# <a name="compiler-error-c3550"></a>Ошибка компилятора C3550

только неструктурированный описатель "decltype(auto)" разрешен в этом контексте

Если `decltype(auto)` используется как заполнитель для типа возвращаемого значения функции, он должен применяться сам по себе. Невозможно использовать его как часть объявления указателя (`decltype(auto*)`), объявления ссылки (`decltype(auto&)`) или любой другого подобного объявления.

## <a name="see-also"></a>См. также

[auto](../../cpp/auto-cpp.md)