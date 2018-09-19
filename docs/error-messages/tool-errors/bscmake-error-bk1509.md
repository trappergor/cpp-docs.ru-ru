---
title: Ошибка BSCMAKE BK1509 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1509
dev_langs:
- C++
helpviewer_keywords:
- BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 091fab63737c7ee1b3b85753a354bb7214cfa411
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025247"
---
# <a name="bscmake-error-bk1509"></a>Ошибка BSCMAKE BK1509

хватает размера кучи

BSCMAKE не хватило памяти, включая виртуальной памяти.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Освободите место на диске.

1. Увеличьте размер файла подкачки.

1. Увеличьте размер файла подкачки Windows.

1. Сократите памяти, требуемой BSCMAKE, с помощью /Ei или/ES, чтобы исключить некоторые входные файлы или /Em, чтобы удалить тело макроса.