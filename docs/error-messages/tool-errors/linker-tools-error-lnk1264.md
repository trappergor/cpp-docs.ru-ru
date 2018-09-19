---
title: Ошибка средств компоновщика LNK1264 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1264
dev_langs:
- C++
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8232e83774dc53755b77ad9c8b3bbb2a0bcc6ae6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102753"
---
# <a name="linker-tools-error-lnk1264"></a>Ошибка средств компоновщика LNK1264

/ LTCG: PGINSTRUMENT указан, но не требуется создание кода; не удалось выполнить инструментирование

**/ LTCG: PGINSTRUMENT** был указан, но OBJ-файлы, скомпилированные с [/GL](../../build/reference/gl-whole-program-optimization.md). Инструментирование не может принимать месте и отказ канала. Должен существовать по крайней мере один OBJ-файл в командной строке, который компилируется с **/GL** таким образом, чтобы инструментирование может произойти.

Профильная оптимизация (PGO) доступна только в 64-разрядных компиляторов.