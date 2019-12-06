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
ms.openlocfilehash: 7f059afe02cbbad77920fd8c4a0e6cb7c958e992
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857363"
---
# <a name="obsolete-calling-conventions"></a>Устаревшие соглашения о вызовах

**Блок, относящийся только к системам Майкрософт**

Соглашения о вызовах **__pascal**, **__fortran**и **__syscall** больше не поддерживаются. Их функциональные возможности можно эмулировать с помощью одного из поддерживаемых соглашений о вызовах и соответствующих параметров компоновщика.

\<Windows. h > теперь поддерживает макрос WINAPI, который преобразуется в соответствующее соглашение о вызовах для целевого объекта. Используйте WINAPI, где ранее использовался стиль PASCAL или **__far \__pascal**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[Передача аргументов и соглашения об именовании](../cpp/argument-passing-and-naming-conventions.md)