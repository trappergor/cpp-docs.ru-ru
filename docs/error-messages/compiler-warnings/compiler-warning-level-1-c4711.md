---
title: Предупреждение компилятора (уровень 1) C4711 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4711
dev_langs:
- C++
helpviewer_keywords:
- C4711
ms.assetid: 270506ab-fead-4328-b714-2978113be238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d184d5043dad1138f774ca7288a773bcc38c6d9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069954"
---
# <a name="compiler-warning-level-1-c4711"></a>Предупреждение компилятора (уровень 1) C4711

функция "функция" выбрана для подстановки

Компилятор выполнил подстановку кода указанной функции, несмотря на то, что он не был помечен для встраивания.

C4711 доступен в том случае, если [/Ob2](../../build/reference/ob-inline-function-expansion.md) указан.

Встраивание кода выполняется по своему усмотрению компилятора. Это предупреждение носит информационный характер.

Это предупреждение отключено по умолчанию. Чтобы включить предупреждение, используйте [#pragma warning](../../preprocessor/warning.md). Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .