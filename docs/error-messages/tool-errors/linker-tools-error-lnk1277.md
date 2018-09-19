---
title: Ошибка средств компоновщика LNK1277 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1277
dev_langs:
- C++
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 542c48bd23b3f84ab301404987c77d964f51823e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082542"
---
# <a name="linker-tools-error-lnk1277"></a>Ошибка средств компоновщика LNK1277

запись объекта не найдена в pgd (имя файла)

При использовании [/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), путь к одной из входных файлов LIB "," def "или" obj отличался от пути, на котором они были найдены во время/LTCG: PGINSTRUMENT. Это может объясняться изменение в переменной среды LIB после/LTCG: PGINSTRUMENT. Полный путь к входных файлов хранится в PGD-файла.

/ LTCG: PGOPTIMIZE требует идентична на этапе/LTCG: PGINSTRUMENT входные данные.

Чтобы устранить это предупреждение, выполните одно из следующих действий.

- Запуск/LTCG: PGINSTRUMENT, вернуть все тестовые запуски и запустите/LTCG: PGOPTIMIZE.

- Изменение переменной среды LIB существовавшие при запуске/LTCG: PGINSTRUMENT.

Не рекомендуется решить LNK1277 с использованием/LTCG: PGUPDATE.