---
title: Ошибка компилятора ресурсов RC2001 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2001
dev_langs:
- C++
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d75d0f906ba0d7be75ca5177bc1f58bccd226251
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039976"
---
# <a name="resource-compiler-error-rc2001"></a>Ошибка компилятора ресурсов RC2001

NewLine в константе

Строковая константа была продолжена на следующую строку без либо обратную косую черту (**\\**) или закрытия и открытия двойные кавычки (**"**).

Чтобы приостановить выполнение строковая константа, которая находится на две строки в исходном файле, выполните одно из следующих:

- Окончание первую строку начинают с символ продолжения строки, обратной косой черты.

- Закройте строками на первую строку начинают с двойной кавычки и откройте строку на следующей строке другими двойными кавычками.

Недостаточно для завершения первую строку начинают с \n, escape-последовательность для внедрения символа новой строки в строковую константу.