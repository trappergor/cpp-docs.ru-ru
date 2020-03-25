---
title: Предупреждение компилятора (уровень 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: 7de4cdf0eacb1b9848a4350f1d223da1fd47d1fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198306"
---
# <a name="compiler-warning-level-4-c4611"></a>Предупреждение компилятора (уровень 4) C4611

взаимодействие между "Function" и C++ уничтожением объектов не является переносимым

На некоторых платформах функции, включающие **catch** , могут C++ не поддерживать семантику объектов уничтожения, если она находится вне области действия.

Чтобы избежать непредвиденного поведения, Избегайте использования функции **catch** в функциях, имеющих конструкторы и деструкторы.

Это предупреждение выдается только один раз. см. [предупреждение pragma](../../preprocessor/warning.md).
