---
title: Неустранимая ошибка C1305 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1305
dev_langs:
- C++
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4beb1140d161b8cbe54cab40dcc72899c976edc3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048751"
---
# <a name="fatal-error-c1305"></a>Неустранимая ошибка C1305

База данных профилей «PGD-файл» предназначена для другой архитектуры

PGD-файл, который был создан из операции/LTCG: PGINSTRUMENT для другой платформы передан [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Оптимизация, зависимая от профиля](../../build/reference/profile-guided-optimizations.md) доступны для платформ x86 и x64. Тем не менее PGD-файл, созданный с помощью операции/LTCG: PGINSTRUMENT для одной платформы не является допустимым как входные данные для разных платформ / LTCG: PGOPTIMIZE.

Чтобы устранить эту ошибку, необходимо только передайте PGD-файл, который создается с помощью/LTCG: PGINSTRUMENT для/LTCG: PGOPTIMIZE на той же платформе.