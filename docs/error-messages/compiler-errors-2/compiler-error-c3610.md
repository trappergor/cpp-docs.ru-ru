---
title: Ошибка компилятора C3610 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3610
dev_langs:
- C++
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b46b3669978ff3735d5a16015ca0a01e65f07ae9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037857"
---
# <a name="compiler-error-c3610"></a>Ошибка компилятора C3610

«тип_значения»: тип значения должен быть «упакован» перед вызовом метода «метод»

По умолчанию тип значения не в управляемой куче. Перед вызовом методов из классов среды выполнения .NET, такие как `Object`, необходимо переместить тип значения в управляемой куче.

C3610 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.
