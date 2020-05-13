---
title: Ошибка компилятора C2708
ms.date: 11/04/2016
f1_keywords:
- C2708
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
ms.openlocfilehash: a1d3379a0da42c5aabd38cffbf6f6a3f340ef3b9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202375"
---
# <a name="compiler-error-c2708"></a>Ошибка компилятора C2708

"идентификатор": длина фактических параметров в байтах отличается от предыдущего вызова или ссылки

Функции [__stdcall](../../cpp/stdcall.md) должен предшествовать прототип. В противном случае компилятор интерпретирует первый вызов функции как прототип, и эта ошибка возникает, когда компилятор обнаруживает несовпадающий вызов.

Чтобы устранить эту ошибку, добавьте прототип функции.
