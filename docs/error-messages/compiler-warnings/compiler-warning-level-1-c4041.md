---
title: Предупреждение компилятора (уровень 1) C4041 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4041
dev_langs:
- C++
helpviewer_keywords:
- C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ff2c8066557e420ecd7de561d7731b7be733315
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085788"
---
# <a name="compiler-warning-level-1-c4041"></a>Предупреждение компилятора (уровень 1) C4041

ограничение компилятора: завершение вывода браузера

Информация для браузера превысила установленный для компилятора предел.

Это предупреждение может быть вызвано компиляцией с параметром [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (информация для браузера включает локальные переменные).

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Выполните компиляцию с параметром /Fr (информация для браузера без локальных переменных).

1. Отключите вывод информации для браузера (выполните компиляцию без параметра /FR или /Fr).