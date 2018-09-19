---
title: Ошибка средств компоновщика LNK1201 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1201
dev_langs:
- C++
helpviewer_keywords:
- LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c133748f95846160e1387e31e023d9ce459b281
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055279"
---
# <a name="linker-tools-error-lnk1201"></a>Ошибка средств компоновщика LNK1201

Ошибка при записи в базу данных программы «имя_файла»; Проверьте недостаточно места на диске, недопустимый путь или недостаточно прав

Не удалось записать ССЫЛКУ на базу данных программы (PDB) для выходного файла.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Файл поврежден. Удалите PDB-файл и повторно скомпоновать.

1. Недостаточно дискового пространства для записи файла.

1. Диск недоступен из-за проблемы с сетью.

1. Отладчик активен в программу, которую вы пытаетесь подключиться.

1. Хватает размера кучи.  См. в разделе [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) Дополнительные сведения.