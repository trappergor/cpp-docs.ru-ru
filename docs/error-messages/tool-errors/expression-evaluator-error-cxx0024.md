---
title: Ошибка вычислителя выражений CXX0024 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0024
dev_langs:
- C++
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2816be7bb1d33757d9722d605d461ac6fb34fadd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118199"
---
# <a name="expression-evaluator-error-cxx0024"></a>Ошибка вычислителя выражений CXX0024

операции требуется левостороннее значение

Выражение, результатом является l значением которого был указан для операции, требующей l значением.

L значение (так называемых, так как он отображается в левой части оператора присваивания) — это выражение, ссылающееся на расположение в памяти.

Например `buffer[count]` является допустимым l значением, так как он указывает конкретное расположение в памяти. Логическое сравнение `zed != 0` не является допустимым l значением, так как его результатом является значение TRUE или FALSE, а не адрес памяти.

Эта ошибка идентична ошибке CAN0024.