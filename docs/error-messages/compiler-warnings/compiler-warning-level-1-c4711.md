---
title: Предупреждение компилятора (уровень 1) C4711
ms.date: 11/04/2016
f1_keywords:
- C4711
helpviewer_keywords:
- C4711
ms.assetid: 270506ab-fead-4328-b714-2978113be238
ms.openlocfilehash: 9e2adf3583012a670f936c2b86a9ddc393fe53c6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175341"
---
# <a name="compiler-warning-level-1-c4711"></a>Предупреждение компилятора (уровень 1) C4711

функция "функция" выбрана для подстановки

Компилятор выполнил встраивание для данной функции, хотя он не был помечен для встраивания.

C4711 включается, если указан [/Ob2](../../build/reference/ob-inline-function-expansion.md) .

Встраивание выполняется по усмотрению компилятора. Это предупреждение носит информационный характер.

Это предупреждение отключено по умолчанию. Чтобы включить предупреждение, используйте [#pragma предупреждение](../../preprocessor/warning.md). Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .
