---
title: Предупреждение компилятора (уровень 1) C4952
ms.date: 08/27/2018
f1_keywords:
- C4952
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
ms.openlocfilehash: 560705edeb0bbdd6be760736a8d4a19d914133d2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174574"
---
# <a name="compiler-warning-level-1-c4952"></a>Предупреждение компилятора (уровень 1) C4952

> "*функция*": данные профилирования не найдены в базе данных программы "*pgd_file*"

При использовании параметра [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)компилятор обнаружил модуль ввода, который был перекомпилирован после `/LTCG:PGINSTRUMENT` и имеет новую функцию (*функция*).

Это предупреждение носит информационный характер. Чтобы решить проблему, связанную с этим предупреждением, запустите `/LTCG:PGINSTRUMENT`, повторите все тестовые запуски и запустите `/LTCG:PGOPTIMIZE`.

Вместо этого предупреждения будет ошибка, если использовался параметр `/LTCG:PGOPTIMIZE` .
