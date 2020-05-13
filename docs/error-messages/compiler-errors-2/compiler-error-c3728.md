---
title: Ошибка компилятора C3728
ms.date: 11/04/2016
f1_keywords:
- C3728
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
ms.openlocfilehash: 8aec3ae1ff629ef7fa000182cde29e306a471315
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165879"
---
# <a name="compiler-error-c3728"></a>Ошибка компилятора C3728

"событие": событие не имеет метода Raise

Метаданные, созданные с помощью языка, такие C#как, который не позволяет создавать событие извне класса, в котором он был определен, был добавлен в директиву [#using](../../preprocessor/hash-using-directive-cpp.md) , и визуальная C++ программа, использующая программирование CLR, попыталась вызвать событие.

Чтобы создать событие в программе C#, разработанной на языке, например, класс, содержащий событие, должен также определять открытый метод, который вызывает событие.
