---
title: Предупреждение BSCMAKE BK4502 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK4502
- BK1513
dev_langs:
- C++
helpviewer_keywords:
- BK1513
- BK4502
ms.assetid: ee412ec8-df03-4cdb-91ee-5d609ded8691
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4142993b3f4f5bda2b3e4ce322aa26d7beca8584
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056330"
---
# <a name="bscmake-warning-bk4502"></a>Предупреждение BSCMAKE BK4502

усечение. SBR-файл «имя_файла», не в имя файла

SBR-пустой файл, который не был изначально частью BSC-файл был указан во время обновления.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Задано неверное имя файла.

1. Файл удален. (Ошибка [BK1513](../../error-messages/tool-errors/bscmake-error-bk1513.md) результатов.)

1. Файл поврежден, BSCMAKE необходимо выполнить полное построение.