---
title: Функция exit
ms.date: 11/04/2016
f1_keywords:
- Exit
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
ms.openlocfilehash: 82c9d00a49c8a080d893a51052739a0265ad0860
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154442"
---
# <a name="exit-function"></a>Функция exit

**Выйти из** функции, объявленные в стандартном включаемом файле \<stdlib.h >, завершает программу C++.

Значение, указанное в качестве аргумента **выйти из** возвращается в операционную систему, как ее возвращаемое код или код выхода. Принято, чтобы нулевым кодом возврата обозначалось, что программа завершена успешно.

> [!NOTE]
>  Можно использовать константы, EXIT_FAILURE и EXIT_SUCCESS, определенные в \<stdlib.h >, чтобы указать на успех или сбой программы.

Выдача **возвращают** инструкции от `main` функция эквивалентно вызову **выйти из** функции с возвращаемым значением в качестве аргумента.

Дополнительные сведения см. в разделе [выйти из](../c-runtime-library/reference/exit-exit-exit.md) в *Справочник по библиотеке времени выполнения*.

## <a name="see-also"></a>См. также

[Завершение программы](../cpp/program-termination.md)