---
title: Ошибка компилятора C2696
ms.date: 11/04/2016
f1_keywords:
- C2696
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
ms.openlocfilehash: 340a5d0596160b6c9c7bcfc78aed812f8c5f3fa3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367607"
---
# <a name="compiler-error-c2696"></a>Ошибка компилятора C2696

Не удается создать временный объект управляемого типа «тип»

Ссылки на `const` в неуправляемой программе при компиляции вызовите конструктор и создать временный объект в стеке. Тем не менее управляемый класс никогда не могут создаваться в стеке.

C2696 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.
