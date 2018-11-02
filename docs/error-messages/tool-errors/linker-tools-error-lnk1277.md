---
title: Ошибка средств компоновщика LNK1277
ms.date: 11/04/2016
f1_keywords:
- LNK1277
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
ms.openlocfilehash: 137aa15dd9dad4b08d52af55da60a9cdf8b58055
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662076"
---
# <a name="linker-tools-error-lnk1277"></a>Ошибка средств компоновщика LNK1277

запись объекта не найдена в pgd (имя файла)

При использовании [/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), путь к одной из входных файлов LIB "," def "или" obj отличался от пути, на котором они были найдены во время/LTCG: PGINSTRUMENT. Это может объясняться изменение в переменной среды LIB после/LTCG: PGINSTRUMENT. Полный путь к входных файлов хранится в PGD-файла.

/ LTCG: PGOPTIMIZE требует идентична на этапе/LTCG: PGINSTRUMENT входные данные.

Чтобы устранить это предупреждение, выполните одно из следующих действий.

- Запуск/LTCG: PGINSTRUMENT, вернуть все тестовые запуски и запустите/LTCG: PGOPTIMIZE.

- Изменение переменной среды LIB существовавшие при запуске/LTCG: PGINSTRUMENT.

Не рекомендуется решить LNK1277 с использованием/LTCG: PGUPDATE.