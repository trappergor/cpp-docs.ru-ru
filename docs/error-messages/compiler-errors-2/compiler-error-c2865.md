---
title: Ошибка компилятора C2865 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2865
dev_langs:
- C++
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc0a49f8e6ab42f7e607cd5f4f7cc91f6895abe0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035172"
---
# <a name="compiler-error-c2865"></a>Ошибка компилятора C2865

«функция»: недопустимое сравнение для дескриптора_или_указателя

Вы можете сравнить ссылки на [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md) или управляемых ссылочных типов только на предмет равенства, чтобы увидеть, если они ссылаются на один и тот же объект (==) или на разные объекты (! =).

Невозможно сравнить их для сортировки, так как среда выполнения .NET может переместить управляемые объекты в любой момент изменить результат теста.