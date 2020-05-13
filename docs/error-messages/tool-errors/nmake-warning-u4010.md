---
title: Предупреждение программы NMAKE U4010
ms.date: 11/04/2016
f1_keywords:
- U4010
helpviewer_keywords:
- U4010
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
ms.openlocfilehash: f68da1893eec6325ccccfd0e2e2dd0e612f28eb9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193138"
---
# <a name="nmake-warning-u4010"></a>Предупреждение программы NMAKE U4010

"целевой объект": сбой сборки; Указан/k, продолжение...

Команда в блоке команд для данного целевого объекта вернула ненулевой код выхода. Параметр/K сообщает NMAKE, чтобы продолжить обработку несвязанных частей сборки и выдать код выхода 1 после завершения сеанса NMAKE.

Если заданный целевой объект является, зависимым от другого целевого объекта, NMAKE выдает предупреждение [U4011](../../error-messages/tool-errors/nmake-warning-u4011.md) после этого предупреждения.
