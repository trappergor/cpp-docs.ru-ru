---
title: Компилятор предупреждение (уровень 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 04732619571420e777244b81bf4b93b775477a20
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582576"
---
# <a name="compiler-warning-level-1-c4124"></a>Компилятор предупреждение (уровень 1) C4124

__fastcall с проверкой стека неэффективно

`__fastcall` Было использовано ключевое слово при включенном режиме проверки стека.

`__fastcall` Соглашение создает код быстрее, но проверка стека замедляет. При использовании `__fastcall`, отключить проверку стека с **check_stack** директивы pragma или/GS.

Это предупреждение выдается только для первой функции, объявленной в этих условиях.