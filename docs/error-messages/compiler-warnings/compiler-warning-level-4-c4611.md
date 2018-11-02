---
title: Предупреждение компилятора (уровень 4) C4611
ms.date: 11/04/2016
f1_keywords:
- C4611
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
ms.openlocfilehash: b799c568d73a081a4d4cf5616f376f3efc9eeffb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542315"
---
# <a name="compiler-warning-level-4-c4611"></a>Предупреждение компилятора (уровень 4) C4611

взаимодействие между «function» и деструктором объектов C++ не будет переносимым

На некоторых платформах функции, включающие **catch** может не поддерживают семантику объекта C++ уничтожения при выходе за область.

Чтобы избежать непредсказуемого поведения, избегайте использования **catch** в функции, которые имеют конструкторы и деструкторы.

Это предупреждение выдается только один раз; см. в разделе [в директиве pragma warning](../../preprocessor/warning.md).