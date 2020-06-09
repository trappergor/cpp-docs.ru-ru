---
title: Управление памятью. Выделение кучи
ms.date: 11/04/2016
helpviewer_keywords:
- memory [MFC], detecting leaks
- delete operator [MFC], using with debug MFC
- heap allocation [MFC], described
- memory allocation [MFC], heap memory
- memory leaks [MFC], detecting
- new operator [MFC], using with debug MFC
- heap allocation [MFC]
- detecting memory leaks [MFC]
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
ms.openlocfilehash: 1f0b07a0a3439faba71078af1e2d7d1559a42b41
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626285"
---
# <a name="memory-management-heap-allocation"></a>Управление памятью. Выделение кучи

Куча резервируется для потребностей в выделении памяти для программы. Это область, расположенная отдельно от программного кода и стека. Обычные программы на языке C используют функции **malloc** и Free для выделения и **освобождения** памяти кучи. Отладочная версия MFC предоставляет измененные версии встроенных операторов C++ **New** и **Delete** для выделения и освобождения объектов в памяти кучи.

При использовании функций **New** и **Delete** вместо **malloc** и **Free**вы можете воспользоваться усовершенствованными возможностями отладки управления памятью библиотеки классов, которые могут быть полезны при обнаружении утечек памяти. При создании программы с использованием окончательной версии MFC стандартные версии операторов **New** и **Delete** предоставляют эффективный способ выделения и освобождения памяти (окончательная версия MFC не предоставляет измененные версии этих операторов).

Обратите внимание, что общий размер объектов, выделенных в куче, ограничен только доступной виртуальной памятью вашей системы.

## <a name="see-also"></a>См. также раздел

[Управление памятью](memory-management.md)
