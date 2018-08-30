---
title: Предупреждение компилятора (уровень 1) C4953 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4953
dev_langs:
- C++
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e53808d4ad97bad4eccdf81b0a863277f8f7796
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194636"
---
# <a name="compiler-warning-level-1-c4953"></a>Предупреждение компилятора (уровень 1) C4953

> Встраиваемого метода "*функция*" изменена после профилирования были собраны данные, данные профилирования не используются

При использовании [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), компилятор обнаружил входной модуль, который был перекомпилирован после `/LTCG:PGINSTRUMENT` и содержит функцию (*функция*) и в котором выполняется определенный тест функции является кандидатом для встраивания. Однако после перекомпиляции модуля функция больше не является кандидатом для встраивания.

Это предупреждение носит информационный характер. Чтобы решить проблему, связанную с этим предупреждением, запустите `/LTCG:PGINSTRUMENT`, повторите все тестовые запуски и запустите `/LTCG:PGOPTIMIZE`.

Вместо этого предупреждения будет ошибка, если использовался параметр `/LTCG:PGOPTIMIZE` .