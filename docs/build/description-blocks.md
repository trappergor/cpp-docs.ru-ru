---
title: Блоки описания | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d83e010f690f96afa5a57eb89ca1e8f4cf444225
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699664"
---
# <a name="description-blocks"></a>Блоки описания

Блок описания — строка зависимости, при желании указав через блок команд:

```
targets... : dependents...
    commands...
```

Строка зависимости определяет один или несколько целевых объектов и ноль или более зависимых элементов. Целевой объект должен находиться в начале строки. Допускаются отдельных целевых объектов из зависимых компонентов с помощью символа двоеточия (:), пробелы или символы табуляции. Чтобы разделить строку, используйте обратную косую черту (\) после цели или зависимых. Если целевой объект не существует, имеет более раннюю временную метку, чем зависимый или является [псевдоцелью](../build/pseudotargets.md), NMAKE выполняет команды. Если зависимый является целевым объектом в другом месте и не существует или является устаревшей по отношению к собственным зависимостям, NMAKE обновляет зависимой перед обновлением текущей зависимости.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

[Целевые объекты](../build/targets.md)

[Зависимые элементы](../build/dependents.md)

## <a name="see-also"></a>См. также

[Справочник по программе NMAKE](../build/nmake-reference.md)