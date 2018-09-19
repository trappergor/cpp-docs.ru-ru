---
title: Ошибка компилятора C2696 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2696
dev_langs:
- C++
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6e76b0c11d329c734b0609c540aca4315c7ed9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108746"
---
# <a name="compiler-error-c2696"></a>Ошибка компилятора C2696

Не удается создать временный объект управляемого типа «тип»

Ссылки на `const` в неуправляемой программе при компиляции вызовите конструктор и создать временный объект в стеке. Тем не менее управляемый класс никогда не могут создаваться в стеке.

C2696 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.
