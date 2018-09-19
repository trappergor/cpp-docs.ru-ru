---
title: Ошибка вычислителя выражений CXX0015 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0015
dev_langs:
- C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1aa37a2cc7208063ce4cfa786de196842ab42b45
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050820"
---
# <a name="expression-evaluator-error-cxx0015"></a>Ошибка вычислителя выражений CXX0015

слишком сложное выражение (переполнение стека)

Введенное выражение было слишком сложным или вложенные слишком глубоко объема хранилища для вычислитель выражений C.

Переполнение обычно происходит из-за слишком большого количества незавершенных вычислений.

Перестройте выражение так, чтобы каждый компонент выражения можно вычислить, в котором он находится, а не ждать, пока другие части выражения, которые необходимо вычислить.

Разбейте выражение на несколько команд.

Эта ошибка идентична CAN0015.