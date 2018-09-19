---
title: Предупреждение компилятора (уровень 1) C4651 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4651
dev_langs:
- C++
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b516ef86372901d00dd20d94ed10d5e361bbab8d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099477"
---
# <a name="compiler-warning-level-1-c4651"></a>Предупреждение компилятора (уровень 1) C4651

«Определение» указан для предкомпилированного заголовка, но не для текущей компиляции

Определение указан в том случае, когда был создан предкомпилированный заголовок, но не в этой компиляции.

Определение будет действовать в предкомпилированный заголовок, но не в остальной части кода.

Если предварительно скомпилированный заголовок был построен с помощью/DSYMBOL, компилятор выдаст это предупреждение, если /Yu компиляции не имеет значение/DSYMBOL.  Добавление в командную строку /Yu значение/DSYMBOL разрешает это предупреждение.