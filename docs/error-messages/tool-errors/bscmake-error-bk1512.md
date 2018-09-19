---
title: Ошибка BSCMAKE BK1512 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1512
dev_langs:
- C++
helpviewer_keywords:
- BK1512
ms.assetid: 0a626ff3-63db-4797-abe4-31545ce2c2c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ce429c0c4cf0300b3818a9be9d28fd03e95f5eb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039859"
---
# <a name="bscmake-error-bk1512"></a>Ошибка BSCMAKE BK1512

Имя файла: превышена емкость

BSCMAKE не может создать файл информации, так как превышает количество определений, ссылки, модули и другие сведения.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Исключите некоторые сведения, с помощью /Em/es и /Ei.

1. Не указывайте параметр /Iu.