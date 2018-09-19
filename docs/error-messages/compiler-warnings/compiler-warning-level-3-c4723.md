---
title: Предупреждение компилятора (уровень 3) C4723 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4723
dev_langs:
- C++
helpviewer_keywords:
- C4723
ms.assetid: 07669d14-3fd8-4a43-94bc-b61c50e58460
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ca6715e26705632dc3187cb6db7deed8636cd82
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033151"
---
# <a name="compiler-warning-level-3-c4723"></a>Предупреждение компилятора (уровень 3) C4723

возможное деление на 0

Второй операнд в операции деления на ноль во время компиляции, предоставляя неопределенным результатам.

Это предупреждение выдается только в том случае, при использовании [/Og](../../build/reference/og-global-optimizations.md) или параметра оптимизации, подразумевает /Og.

Компилятор мог создать операнд, равный нулю.