---
title: Неустранимая ошибка C1305
ms.date: 11/04/2016
f1_keywords:
- C1305
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
ms.openlocfilehash: 988842a0d5e8002ffd1478a2e10a8c88ee971911
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822240"
---
# <a name="fatal-error-c1305"></a>Неустранимая ошибка C1305

База данных профилей «PGD-файл» предназначена для другой архитектуры

PGD-файл, который был создан из операции/LTCG: PGINSTRUMENT для другой платформы передан [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Оптимизация, зависимая от профиля](../../build/profile-guided-optimizations.md) доступны для платформ x86 и x64. Тем не менее PGD-файл, созданный с помощью операции/LTCG: PGINSTRUMENT для одной платформы не является допустимым как входные данные для разных платформ / LTCG: PGOPTIMIZE.

Чтобы устранить эту ошибку, необходимо только передайте PGD-файл, который создается с помощью/LTCG: PGINSTRUMENT для/LTCG: PGOPTIMIZE на той же платформе.