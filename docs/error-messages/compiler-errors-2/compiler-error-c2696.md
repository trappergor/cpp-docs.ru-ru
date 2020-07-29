---
title: Ошибка компилятора C2696
ms.date: 11/04/2016
f1_keywords:
- C2696
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
ms.openlocfilehash: f6af217dbcd871ac4edd1852042144802388545b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216093"
---
# <a name="compiler-error-c2696"></a>Ошибка компилятора C2696

Невозможно создать временный объект управляемого типа "тип"

**`const`** В неуправляемой программе компилятор вызывает конструктор и создает временный объект в стеке. Однако управляемый класс никогда не может быть создан в стеке.

C2696 доступен только при использовании устаревшего параметра компилятора **/clr: oldSyntax**.
