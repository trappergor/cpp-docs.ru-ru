---
title: Предупреждение компилятора (уровень 1) C4729 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4729
dev_langs:
- C++
helpviewer_keywords:
- C4729
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d1f5b4fe452937ce74e56886a5214ff92f44af7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096084"
---
# <a name="compiler-warning-level-1-c4729"></a>Предупреждение компилятора (уровень 1) C4729

слишком большая функция для предупреждений, основанных на оптимизации структуры кода

Это предупреждение возникает в случае, если функция слишком велика для компиляции с надежной проверкой ситуаций, в которых могут возникать предупреждения. Это предупреждение появляется только в том случае, если используется параметр компилятора [/Od](../../build/reference/od-disable-debug.md) .

Чтобы устранить это предупреждение, разделите функцию на более мелкие функции.