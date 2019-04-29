---
title: Ошибка BSCMAKE BK1509
ms.date: 11/04/2016
f1_keywords:
- BK1509
helpviewer_keywords:
- BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
ms.openlocfilehash: 384f202ea3eb969da2ce3a3b82209c383009c62e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279532"
---
# <a name="bscmake-error-bk1509"></a>Ошибка BSCMAKE BK1509

хватает размера кучи

BSCMAKE не хватило памяти, включая виртуальной памяти.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Освободите место на диске.

1. Увеличьте размер файла подкачки.

1. Увеличьте размер файла подкачки Windows.

1. Сократите памяти, требуемой BSCMAKE, с помощью /Ei или/ES, чтобы исключить некоторые входные файлы или /Em, чтобы удалить тело макроса.