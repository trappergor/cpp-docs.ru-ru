---
title: Предупреждение (уровень 1) C4124 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a69190487c22987ead2d00ec102785ed42ea93c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090936"
---
# <a name="compiler-warning-level-1-c4124"></a>Компилятор предупреждение (уровень 1) C4124

__fastcall с проверкой стека неэффективно

`__fastcall` Было использовано ключевое слово при включенном режиме проверки стека.

`__fastcall` Соглашение создает код быстрее, но проверка стека замедляет. При использовании `__fastcall`, отключить проверку стека с **check_stack** директивы pragma или/GS.

Это предупреждение выдается только для первой функции, объявленной в этих условиях.