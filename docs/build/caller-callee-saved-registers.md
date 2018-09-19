---
title: Сохраняемые регистры вызываемого объектов вызывающий объект | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8e877387dbb5b0be865e11017a3ac71a0c38faa
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707659"
---
# <a name="callercallee-saved-registers"></a>Сохраняемые регистры вызываемого и вызывающего объектов

Регистры RAX, RCX, RDX, R8, R9, R10, R11 считаются временными и необходимо учитывать уничтожаются при вызове функции (если в противном случае безопасность проверяемыми в процессе анализа, такие как оптимизация всей программы).

Регистры RBX, RBP, RDI, RSI, RSP, R12, R13, R14 и R15 считаются энергонезависимой и необходимо сохранить и восстановить с помощью функции, использует их.

## <a name="see-also"></a>См. также

[Соглашение о вызовах](../build/calling-convention.md)