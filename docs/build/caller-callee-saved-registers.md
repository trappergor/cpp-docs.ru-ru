---
title: Сохраняемые регистры вызываемого объектов вызывающего объекта
ms.date: 11/04/2016
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
ms.openlocfilehash: f34fbfff8e6c61b5d568c073f6b7da2a12e34535
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654705"
---
# <a name="callercallee-saved-registers"></a>Сохраняемые регистры вызываемого и вызывающего объектов

Регистры RAX, RCX, RDX, R8, R9, R10, R11 считаются временными и необходимо учитывать уничтожаются при вызове функции (если в противном случае безопасность проверяемыми в процессе анализа, такие как оптимизация всей программы).

Регистры RBX, RBP, RDI, RSI, RSP, R12, R13, R14 и R15 считаются энергонезависимой и необходимо сохранить и восстановить с помощью функции, использует их.

## <a name="see-also"></a>См. также

[Соглашение о вызовах](../build/calling-convention.md)