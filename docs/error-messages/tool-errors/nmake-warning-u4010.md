---
title: Предупреждение программы NMAKE U4010
ms.date: 11/04/2016
f1_keywords:
- U4010
helpviewer_keywords:
- U4010
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
ms.openlocfilehash: aa4d2355b18a3c6cc6fc3151c7662fbbbaa665d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554262"
---
# <a name="nmake-warning-u4010"></a>Предупреждение программы NMAKE U4010

«целевой объект»: построение завершено сбоем; Указан, продолжение...

Команда в блоке команд для заданного целевого объекта вернула ненулевой код выхода. Параметр /K дал NMAKE продолжать обработку несвязанных частей построения и вывести код выхода 1 при окончании сеанса NMAKE.

Если данный целевой объект сам по себе, является зависимостью для другого целевого объекта (NMAKE) выдает предупреждение [U4011](../../error-messages/tool-errors/nmake-warning-u4011.md) после этого предупреждения.