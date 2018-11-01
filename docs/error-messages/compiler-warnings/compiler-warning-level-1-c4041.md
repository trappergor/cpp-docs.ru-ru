---
title: Предупреждение компилятора (уровень 1) C4041
ms.date: 11/04/2016
f1_keywords:
- C4041
helpviewer_keywords:
- C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
ms.openlocfilehash: 6e1f2a2396447038f6a117f66d4002bea7fd7486
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513676"
---
# <a name="compiler-warning-level-1-c4041"></a>Предупреждение компилятора (уровень 1) C4041

ограничение компилятора: завершение вывода браузера

Информация для браузера превысила установленный для компилятора предел.

Это предупреждение может быть вызвано компиляцией с параметром [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (информация для браузера включает локальные переменные).

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Выполните компиляцию с параметром /Fr (информация для браузера без локальных переменных).

1. Отключите вывод информации для браузера (выполните компиляцию без параметра /FR или /Fr).