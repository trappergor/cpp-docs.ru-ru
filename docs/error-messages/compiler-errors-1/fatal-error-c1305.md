---
title: Неустранимая ошибка C1305
ms.date: 11/04/2016
f1_keywords:
- C1305
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
ms.openlocfilehash: d67f0eabfd0718d8a3e3dd75e96c3e6c0d2266b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623214"
---
# <a name="fatal-error-c1305"></a>Неустранимая ошибка C1305

База данных профилей «PGD-файл» предназначена для другой архитектуры

PGD-файл, который был создан из операции/LTCG: PGINSTRUMENT для другой платформы передан [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Оптимизация, зависимая от профиля](../../build/reference/profile-guided-optimizations.md) доступны для платформ x86 и x64. Тем не менее PGD-файл, созданный с помощью операции/LTCG: PGINSTRUMENT для одной платформы не является допустимым как входные данные для разных платформ / LTCG: PGOPTIMIZE.

Чтобы устранить эту ошибку, необходимо только передайте PGD-файл, который создается с помощью/LTCG: PGINSTRUMENT для/LTCG: PGOPTIMIZE на той же платформе.