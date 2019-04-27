---
title: Устаревшие соглашения о вызовах
ms.date: 11/04/2016
f1_keywords:
- __fortran
- __pascal
- __syscall
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
ms.openlocfilehash: 86c75c779158d9f191dd015410cf16c9ce25690d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245039"
---
# <a name="obsolete-calling-conventions"></a>Устаревшие соглашения о вызовах

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

**__Pascal**, **__fortran**, и **__syscall** соглашения о вызовах больше не поддерживаются. Их функциональные возможности можно эмулировать с помощью одного из поддерживаемых соглашений о вызовах и соответствующих параметров компоновщика.

\<Windows.h > теперь поддерживает макрос WINAPI, которая преобразуется в соответствующее соглашение о вызовах для целевого объекта. Использовать WINAPI, где вы ранее использовали PASCAL или **__far \__pascal**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Передача аргументов и соглашения об именовании](../cpp/argument-passing-and-naming-conventions.md)