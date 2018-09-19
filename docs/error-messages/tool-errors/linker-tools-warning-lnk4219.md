---
title: Предупреждение средств компоновщика LNK4219 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4219
dev_langs:
- C++
helpviewer_keywords:
- LNK4219
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: daf097cd8715a7c523e6e8a2ea46714481ca7d2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105216"
---
# <a name="linker-tools-warning-lnk4219"></a>Предупреждение средств компоновщика LNK4219

Переполнение адресной привязки имя адресной привязки. Целевой объект «имя целевого символа» выходит за пределы диапазона, вносится преобразователь

Компоновщик вставляет преобразователь в ситуации, где адрес или смещение не умещается в данной инструкции, так как конечный символ находится слишком далеко от расположения инструкции.

Вы можете переупорядочить образ (с помощью [/ORDER](../../build/reference/order-put-functions-in-order.md) параметр, например) чтобы избежать дополнительного уровня косвенного обращения.