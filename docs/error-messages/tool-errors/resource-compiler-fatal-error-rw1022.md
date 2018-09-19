---
title: Неустранимая ошибка компилятора ресурсов RW1022 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW1022
dev_langs:
- C++
helpviewer_keywords:
- RW1022
ms.assetid: 6747c8a9-9c9b-4422-b414-0645d22092d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: caaefc045a31ca64aa9843927d550ef66285cb2e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099854"
---
# <a name="resource-compiler-fatal-error-rw1022"></a>Неустранимая ошибка компилятора ресурсов RW1022

**Ошибка ввода-вывода при записи файл**

Компилятору ресурсов не удалось выполнить запись в файл.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Недостаточно места на диске. Свободное место должно быть равно по крайней мере дважды размер исполняемого файла, который вы создаете.

1. Том доступен только для чтения.

1. Поврежденный сектор.

1. Нарушение общего доступа.