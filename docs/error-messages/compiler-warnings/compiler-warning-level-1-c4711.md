---
title: Предупреждение компилятора (уровень 1) C4711
ms.date: 11/04/2016
f1_keywords:
- C4711
helpviewer_keywords:
- C4711
ms.assetid: 270506ab-fead-4328-b714-2978113be238
ms.openlocfilehash: c10b19b39fcb40527c9e9276f47ecff42ca5a643
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600100"
---
# <a name="compiler-warning-level-1-c4711"></a>Предупреждение компилятора (уровень 1) C4711

функция "функция" выбрана для подстановки

Компилятор выполнил подстановку кода указанной функции, несмотря на то, что он не был помечен для встраивания.

C4711 доступен в том случае, если [/Ob2](../../build/reference/ob-inline-function-expansion.md) указан.

Встраивание кода выполняется по своему усмотрению компилятора. Это предупреждение носит информационный характер.

Это предупреждение отключено по умолчанию. Чтобы включить предупреждение, используйте [#pragma warning](../../preprocessor/warning.md). Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .