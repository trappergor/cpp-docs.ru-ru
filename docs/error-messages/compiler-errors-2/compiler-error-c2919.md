---
title: Ошибка компилятора C2919 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2919
dev_langs:
- C++
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d6ee01e32cd1855855fa6ac071af159be8bac0d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106835"
---
# <a name="compiler-error-c2919"></a>Ошибка компилятора C2919

type: операторы не могут напрямую использоваться на опубликованной поверхности типа WinRT.

Система с типом среды выполнения Windows не поддерживает функции — члены оператора на опубликованной поверхности типа. Это вызвано тем, что не все языки могут использовать функции — члены оператора. Вы можете создать закрытые или внутренние функции — члены оператора, которые можно вызывать из кода C++ в том же классе или блоке компиляции.

Чтобы устранить эту проблему, удалите функцию — член оператора из открытого интерфейса или измените ее на именованную функцию-член. Например, вместо `operator==` назовите функцию-член `Equals`.