---
title: Предупреждение компилятора (уровень 1) C4952 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4952
dev_langs:
- C++
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f62f4c18380d89eb516a5fa49ef63e92ab79a6f2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207155"
---
# <a name="compiler-warning-level-1-c4952"></a>Предупреждение компилятора (уровень 1) C4952

> "*функция*": данные профилирования не найдены в базе данных программы "*PGD-файл*"

При использовании [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), компилятор обнаружил входной модуль, который был перекомпилирован после `/LTCG:PGINSTRUMENT` и имеет новую функцию (*функция*) присутствует.

Это предупреждение носит информационный характер. Чтобы решить проблему, связанную с этим предупреждением, запустите `/LTCG:PGINSTRUMENT`, повторите все тестовые запуски и запустите `/LTCG:PGOPTIMIZE`.

Вместо этого предупреждения будет ошибка, если использовался параметр `/LTCG:PGOPTIMIZE` .