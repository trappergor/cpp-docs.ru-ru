---
title: Предупреждение средств компоновщика LNK4219 | Документы Microsoft
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
ms.openlocfilehash: 59cb7376957b7985b7ae2335ea472171d490ff42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4219"></a>Предупреждение средств компоновщика LNK4219
Переполнение адресной привязки имя адресной привязки. Целевой «имя целевого символа» находится за пределами диапазона, вносится преобразователь  
  
 Компоновщик вставляет преобразователь в ситуации, когда адрес или смещение не удалось помещается в данной инструкции, поскольку целевой символ находится слишком далеко от расположения инструкции.  
  
 Вы можете переупорядочить образ (с помощью [/ORDER](../../build/reference/order-put-functions-in-order.md) вариант, например) во избежание дополнительный уровень косвенного обращения.