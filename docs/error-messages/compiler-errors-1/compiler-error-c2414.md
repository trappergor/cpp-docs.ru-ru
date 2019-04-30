---
title: Ошибка компилятора C2414
ms.date: 11/04/2016
f1_keywords:
- C2414
helpviewer_keywords:
- C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
ms.openlocfilehash: 84fa715c8bd567770f361552e203a37c44ffdde4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402987"
---
# <a name="compiler-error-c2414"></a>Ошибка компилятора C2414

Недопустимое число операторов

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Код операции не поддерживает количество используемых операндов. Проверьте справочное руководство по языка ассемблера, чтобы определить правильное число операндов.

1. Более новый процессор поддерживает инструкцию с различным количеством операндов. Настройка [/arch (минимальная архитектура ЦП)](../../build/reference/arch-minimum-cpu-architecture.md) параметр, чтобы использовать процессор более поздней.