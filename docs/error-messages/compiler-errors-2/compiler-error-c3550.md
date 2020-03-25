---
title: Ошибка компилятора C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: 17c90aa68b29c9490deb8d49895162e8a6bdefec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200776"
---
# <a name="compiler-error-c3550"></a>Ошибка компилятора C3550

только неструктурированный описатель "decltype(auto)" разрешен в этом контексте

Если `decltype(auto)` используется как заполнитель для типа возвращаемого значения функции, он должен применяться сам по себе. Невозможно использовать его как часть объявления указателя (`decltype(auto*)`), объявления ссылки (`decltype(auto&)`) или любой другого подобного объявления.

## <a name="see-also"></a>См. также раздел

[auto](../../cpp/auto-cpp.md)
