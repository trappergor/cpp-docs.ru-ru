---
title: Ошибка компилятора C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 407ed4b30b55b63aa9bf36de9f8675a531d70534
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516237"
---
# <a name="compiler-error-c3744"></a>Ошибка компилятора C3744

для __unhook требуется по крайней мере 3 аргумента в случае управляемых событий

[__Unhook](../../cpp/unhook.md) функция должна принимать три параметра, при использовании в программе, которая компилируется для управляемых расширений для C++.

`__hook` и `__unhook` не совместимы с программированием для/CLR. Вместо этого используйте операторы += и-=.

C3744 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.
