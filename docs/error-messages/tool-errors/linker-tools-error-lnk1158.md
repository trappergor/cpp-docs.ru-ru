---
title: Ошибка средств компоновщика LNK1158
ms.date: 11/04/2016
f1_keywords:
- LNK1158
helpviewer_keywords:
- LNK1158
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
ms.openlocfilehash: 2602c488db660ce067c672df4a746c388d987120
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80184064"
---
# <a name="linker-tools-error-lnk1158"></a>Ошибка средств компоновщика LNK1158

не удается запустить "имяфайла"

Указанный исполняемый файл, вызываемый [Link](../../build/reference/linking.md) , не находится в каталоге, содержащем Link, или в каталоге, указанном в переменной среды PATH.

Например, эта ошибка возникает при попытке использовать параметр PGOPTIMIZE в параметре компоновщика [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) на компьютере с 32-разрядной операционной системой.
