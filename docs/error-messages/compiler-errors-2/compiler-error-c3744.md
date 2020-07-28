---
title: Ошибка компилятора C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 8db81afc348434e9ea2f57c991962fb15dc6bf98
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220162"
---
# <a name="compiler-error-c3744"></a>Ошибка компилятора C3744

__unhook должны иметь по крайней мере 3 аргумента для управляемых событий

[`__unhook`](../../cpp/unhook.md)Функция должна принимать три параметра при использовании в программе, компилируемой для управляемые расширения для C++.

**`__hook`** и **`__unhook`** не совместимы с **`/clr`** программированием. Вместо этого используйте операторы + = и-=.

C3744 доступен только при использовании устаревшего параметра компилятора **`/clr:oldSyntax`** .
