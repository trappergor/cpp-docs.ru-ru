---
title: Ошибка компилятора C2696
ms.date: 11/04/2016
f1_keywords:
- C2696
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
ms.openlocfilehash: 340a5d0596160b6c9c7bcfc78aed812f8c5f3fa3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562880"
---
# <a name="compiler-error-c2696"></a>Ошибка компилятора C2696

Не удается создать временный объект управляемого типа «тип»

Ссылки на `const` в неуправляемой программе при компиляции вызовите конструктор и создать временный объект в стеке. Тем не менее управляемый класс никогда не могут создаваться в стеке.

C2696 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.
