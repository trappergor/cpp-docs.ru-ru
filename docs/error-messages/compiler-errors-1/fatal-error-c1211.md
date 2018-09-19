---
title: Неустранимая ошибка C1211 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1211
dev_langs:
- C++
helpviewer_keywords:
- C1211
ms.assetid: df0ca70d-ec6e-4400-926a-b877e2599978
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 444d2bc25c2eddd5ea9a0170272bd3e71b61f94f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018533"
---
# <a name="fatal-error-c1211"></a>Неустранимая ошибка C1211

Пользовательский атрибут TypeForwardedTo не поддерживается установленной версией среды выполнения

Ошибка C1211 возникает, когда компилятор из текущего выпуска используется со средой CLR из предыдущего выпуска.

Некоторые функциональные возможности компилятора могут не работать в предыдущей версии среды выполнения.

Чтобы устранить ошибку C1211, установите среду CLR, поставляемую вместе с используемым компилятором.

Дополнительные сведения см. в разделе [Переадресация типа (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).