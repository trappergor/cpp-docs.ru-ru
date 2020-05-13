---
title: Ошибка средств компоновщика LNK1277
ms.date: 11/04/2016
f1_keywords:
- LNK1277
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
ms.openlocfilehash: 7c00fb32e4b36eff119195efbb34d536d80df6a9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183661"
---
# <a name="linker-tools-error-lnk1277"></a>Ошибка средств компоновщика LNK1277

запись объекта не найдена в PGD (имя файла)

При использовании [/LTCG: пгоптимзе](../../build/reference/ltcg-link-time-code-generation.md)путь к одному из файлов input. lib, DEF или obj отличается от пути, в котором они были найдены во время/LTCG: PGINSTRUMENT. Это можно объяснить путем изменения переменной среды LIB после/LTCG: PGINSTRUMENT. Полный путь к входным файлам хранится в PGD-файле.

Параметр/LTCG: PGOPTIMIZE требует, чтобы входные данные совпадали с фазой/LTCG: PGINSTRUMENT.

Чтобы устранить это предупреждение, выполните одно из следующих действий.

- Выполните команду/LTCG: PGINSTRUMENT, повторите все тестовые запуски и выполните/LTCG: PGOPTIMIZE.

- Измените переменную среды LIB, чтобы она находилась при выполнении/LTCG: PGINSTRUMENT.

Не рекомендуется обойти LNK1277 с помощью/LTCG: PGUPDATE.
