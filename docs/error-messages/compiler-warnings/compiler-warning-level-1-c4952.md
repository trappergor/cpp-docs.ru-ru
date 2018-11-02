---
title: Предупреждение компилятора (уровень 1) C4952
ms.date: 08/27/2018
f1_keywords:
- C4952
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
ms.openlocfilehash: c2e9b88125655d9ea0abe3e65500b149289ba83b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537583"
---
# <a name="compiler-warning-level-1-c4952"></a>Предупреждение компилятора (уровень 1) C4952

> "*функция*": данные профилирования не найдены в базе данных программы "*PGD-файл*"

При использовании параметра [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)компилятор обнаружил модуль ввода, который был перекомпилирован после `/LTCG:PGINSTRUMENT` и имеет новую функцию (*функция*).

Это предупреждение носит информационный характер. Чтобы решить проблему, связанную с этим предупреждением, запустите `/LTCG:PGINSTRUMENT`, повторите все тестовые запуски и запустите `/LTCG:PGOPTIMIZE`.

Вместо этого предупреждения будет ошибка, если использовался параметр `/LTCG:PGOPTIMIZE` .