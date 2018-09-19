---
title: Ошибка компилятора C3728 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3728
dev_langs:
- C++
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e412824bd2afdadfc21d71b73f38eb8ba5ace82d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108421"
---
# <a name="compiler-error-c3728"></a>Ошибка компилятора C3728

«событие»: событие не имеет метода raise

Метаданные, созданные с помощью языка, такие как C#, который не позволяет создавать событие вне класса, в котором он был определен, вошло в состав [#using](../../preprocessor/hash-using-directive-cpp.md) директивы и программы Visual C++ с помощью программирования событие.

Чтобы породить событие в программе, разработанных на языке, например C#, необходимо также определить открытый метод, который вызывает событие класса, содержащего событие.