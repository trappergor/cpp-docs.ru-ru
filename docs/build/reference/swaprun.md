---
title: -SWAPRUN | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /swaprun
dev_langs:
- C++
helpviewer_keywords:
- /SWAPRUN editbin option
- -SWAPRUN editbin option
- SWAPRUN editbin option
ms.assetid: 6eefd7f3-ca47-48e3-8509-323d27cf4ae7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a93b854dba2855fa68bb3be163cecdcd3570df0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723104"
---
# <a name="swaprun"></a>/SWAPRUN

```
/SWAPRUN:{[!]NET|[!]CD}
```

## <a name="remarks"></a>Примечания

Этот параметр изменяет образ, чтобы операционная система для копирования образа в файл подкачки и запускать ее оттуда. Используйте этот параметр для образов, находящихся в сети или съемный носитель.

Можно добавить или удалить квалификаторы NET или компакт-диска:

- NET указывает, что образ находится в сети.

- Компакт-диска Указывает, что образ находится на компакт-диска или аналогичном съемном носителе.

- Используйте! NET и! Компакт-ДИСК эффектов NET и компакт-диска.

## <a name="see-also"></a>См. также

[Параметры EDITBIN](../../build/reference/editbin-options.md)