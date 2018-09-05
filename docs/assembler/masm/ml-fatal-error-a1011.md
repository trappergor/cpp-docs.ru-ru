---
title: Неустранимая ошибка ML A1011 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1011
dev_langs:
- C++
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32949773b869d189516a381ca7df941760a1e4e4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43690812"
---
# <a name="ml-fatal-error-a1011"></a>Неустранимая ошибка ML A1011

**Директива должна быть в блоке управления**

Ассемблер найти директиву высокого уровня, где не ожидалось только одно. Найдена одна из следующих директив:

- [. ELSE](../../assembler/masm/dot-else.md) без [. IF](../../assembler/masm/dot-if.md)

- [. ENDIF](../../assembler/masm/dot-endif.md) без [. IF](../../assembler/masm/dot-if.md)

- [. ENDW](../../assembler/masm/dot-endw.md) без [. WHILE](../../assembler/masm/dot-while.md)

- [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md) без [. ПОВТОРИТЕ](../../assembler/masm/dot-repeat.md)

- [. По-ПРЕЖНЕМУ](../../assembler/masm/dot-continue.md) без [. ХОТЯ](../../assembler/masm/dot-while.md) или [. ПОВТОРИТЕ](../../assembler/masm/dot-repeat.md)

- [. ПРЕРВАТЬ](../../assembler/masm/dot-break.md) без [. ХОТЯ](../../assembler/masm/dot-while.md) или [. ПОВТОРИТЕ](../../assembler/masm/dot-repeat.md)

- [. ELSE](../../assembler/masm/dot-else.md) ниже `.ELSE`

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>