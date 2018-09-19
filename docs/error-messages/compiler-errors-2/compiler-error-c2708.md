---
title: Ошибка компилятора C2708 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2708
dev_langs:
- C++
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0accd68881cccad5e34530a6c157a4e8179b283
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111099"
---
# <a name="compiler-error-c2708"></a>Ошибка компилятора C2708

«Идентификатор»: длина фактических параметров в байтах отличается от предыдущего вызова или ссылки

Объект [__stdcall](../../cpp/stdcall.md) функции должен предшествовать прототип. В противном случае компилятор интерпретирует первый вызов функции как прототип, и эта ошибка возникает, когда компилятор обнаруживает вызов, который не соответствует.

Чтобы устранить эту ошибку добавьте прототип функции.