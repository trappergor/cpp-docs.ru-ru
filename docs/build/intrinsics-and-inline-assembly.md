---
title: И подставляемый ассемблерный код | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a87e577af339099eda56a3b9d91929a05253a43
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716252"
---
# <a name="intrinsics-and-inline-assembly"></a>Внутренний и подставляемый ассемблерный код

Одно из ограничений для x64 компилятора желательно использовать не поддерживает встроенный ассемблер. Это означает, что функции, не может быть написаны на C или C++, должны записываться в виде подпрограмм или встроенных функций, поддерживаемых компилятором. Некоторые функции, чувствительны к производительности, а другие нет. Функции, чувствительные к производительности должны быть реализованы как встроенные функции.

Компилятор поддерживает встроенные функции описаны в [встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md).

## <a name="see-also"></a>См. также

[Программные соглашения для X64](../build/x64-software-conventions.md)