---
title: Предупреждение компилятора (уровень 3) C4023 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4023
dev_langs:
- C++
helpviewer_keywords:
- C4023
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe457f9a6181fa11b34dd615ad4d5b9637c8bddc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045176"
---
# <a name="compiler-warning-level-3-c4023"></a>Предупреждение компилятора (уровень 3) C4023

"символ": относительный указатель передан в функцию без прототипа: номер параметра

Передача относительного указателя в функцию без прототипа нормализует указатель с непредвиденными результатами.

Чтобы устранить это предупреждение, используйте функции прототипа, которые передаются относительными указателями.