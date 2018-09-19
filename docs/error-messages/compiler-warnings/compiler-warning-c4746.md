---
title: Предупреждение компилятора C4746 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e6abce7ebbcdc41effed05ccf54337e3976c34e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054874"
---
# <a name="compiler-warning-c4746"></a>Предупреждение компилятора C4746

переменное обращение "\<выражение >" может быть/volatile: [iso&#124;ms] параметр; рекомендуется использовать встроенные функции __iso_volatile_load/store.

C4746 создается каждый раз, когда переменная с модификатором volatile осуществляется напрямую. Он предназначен для помощи разработчикам определить расположения кода, которые были затронуты данной указанной в настоящее время volatile модели (которой можно управлять с помощью [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) параметр компилятора). В частности может быть полезно для выявления барьеры памяти оборудования, созданный компилятором, когда используется /volatile:ms.

Чтобы явным образом получить доступ к энергозависимой памяти без влияния непостоянной модели можно использовать встроенные функции __iso_volatile_load/store. С помощью этих встроенных функций не вызовет C4746.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .