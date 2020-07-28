---
title: Предупреждение компилятора (уровень 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 59860bef108a3cd3e8bbbc6ff0790e17dbdaa0d4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214494"
---
# <a name="compiler-warning-level-1-c4124"></a>Предупреждение компилятора (уровень 1) C4124

__fastcall с проверкой стека неэффективна

**`__fastcall`** Ключевое слово было использовано с включенной проверкой стека.

Это **`__fastcall`** соглашение создает более быстрый код, но проверка стека вызывает медленный код. При использовании **`__fastcall`** Отключите проверку стека с помощью директивы pragma **check_stack** или/ГС.

Это предупреждение выдается только для первой функции, объявленной в этих условиях.
