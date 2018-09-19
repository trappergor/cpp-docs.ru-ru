---
title: Неустранимая ошибка NMAKE U1035 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1035
dev_langs:
- C++
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0383bf4742d637d669070efa5370ebda0c7ab159
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019865"
---
# <a name="nmake-fatal-error-u1035"></a>Неустранимая ошибка NMAKE U1035

Синтаксическая ошибка: ожидается ":" или «=» разделителя

Либо двоеточие (**:**) или знак равенства (**=**) ожидался.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Двоеточие не соответствует целевой объект.

1. Двоеточие и пробела (например, ответ) период Однобуквенные целевого объекта. NMAKE интерпретирует это как обозначение диска.

1. Двоеточие не следовали правило определения.

1. Определение макроса не следует знак равенства.

1. Символ после обратной косой черты (**\\**), использованный для переноса команды на новую строку.

1. Отобразилась строка, которая не соответствует любое правило синтаксиса (NMAKE).

1. Makefile был отформатирован с помощью текстовых редакторов.