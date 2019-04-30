---
title: Ошибка компилятора C3610
ms.date: 11/04/2016
f1_keywords:
- C3610
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
ms.openlocfilehash: 9965e6420171b2ea48c8fb7bacc0a5a37ea2f227
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344609"
---
# <a name="compiler-error-c3610"></a>Ошибка компилятора C3610

«тип_значения»: тип значения должен быть «упакован» перед вызовом метода «метод»

По умолчанию тип значения не в управляемой куче. Перед вызовом методов из классов среды выполнения .NET, такие как `Object`, необходимо переместить тип значения в управляемой куче.

C3610 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.
