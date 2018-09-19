---
title: Ошибка компилятора C3744 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3744
dev_langs:
- C++
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d644a621fc6d8e460e1b97e5baec360de8662365
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063727"
---
# <a name="compiler-error-c3744"></a>Ошибка компилятора C3744

для __unhook требуется по крайней мере 3 аргумента в случае управляемых событий

[__Unhook](../../cpp/unhook.md) функция должна принимать три параметра, при использовании в программе, которая компилируется для управляемых расширений для C++.

`__hook` и `__unhook` не совместимы с программированием для/CLR. Вместо этого используйте операторы += и-=.

C3744 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.
