---
title: Неустранимая ошибка C1211
ms.date: 11/04/2016
f1_keywords:
- C1211
helpviewer_keywords:
- C1211
ms.assetid: df0ca70d-ec6e-4400-926a-b877e2599978
ms.openlocfilehash: f39ab027d8d81762ae1cf8f38405f3e21524da2e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781943"
---
# <a name="fatal-error-c1211"></a>Неустранимая ошибка C1211

Пользовательский атрибут TypeForwardedTo не поддерживается установленной версией среды выполнения

Ошибка C1211 возникает, когда компилятор из текущего выпуска используется со средой CLR из предыдущего выпуска.

Некоторые функциональные возможности компилятора могут не работать в предыдущей версии среды выполнения.

Чтобы устранить ошибку C1211, установите среду CLR, поставляемую вместе с используемым компилятором.

Дополнительные сведения см. в разделе [Переадресация типа (C++выполняет)](../../extensions/type-forwarding-cpp-cli.md).