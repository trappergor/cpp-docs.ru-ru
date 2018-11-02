---
title: Ошибка средств компоновщика LNK1264
ms.date: 11/04/2016
f1_keywords:
- LNK1264
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
ms.openlocfilehash: ca17b6946b9e988507af2786825223e042356d0e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505096"
---
# <a name="linker-tools-error-lnk1264"></a>Ошибка средств компоновщика LNK1264

/ LTCG: PGINSTRUMENT указан, но не требуется создание кода; не удалось выполнить инструментирование

**/ LTCG: PGINSTRUMENT** был указан, но OBJ-файлы, скомпилированные с [/GL](../../build/reference/gl-whole-program-optimization.md). Инструментирование не может принимать месте и отказ канала. Должен существовать по крайней мере один OBJ-файл в командной строке, который компилируется с **/GL** таким образом, чтобы инструментирование может произойти.

Профильная оптимизация (PGO) доступна только в 64-разрядных компиляторов.