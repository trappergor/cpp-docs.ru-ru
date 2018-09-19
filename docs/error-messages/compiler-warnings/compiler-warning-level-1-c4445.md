---
title: Предупреждение компилятора (уровень 1) C4445 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4445
dev_langs:
- C++
helpviewer_keywords:
- C4445
ms.assetid: 535e92a0-ba08-4dfc-89b2-af2dcdd7caeb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80b3e13f0f7271a38d71c65efa65f104e44aa475
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079951"
---
# <a name="compiler-warning-level-1-c4445"></a>Предупреждение компилятора (уровень 1) C4445

function: в управляемом типе или типе WinRT виртуальный метод не может быть закрытым

Если виртуальная функция закрытая, у производного типа нет доступа к ней. Чтобы устранить эту ошибку, измените тип доступ виртуальной функции-члена на защищенный или общий.