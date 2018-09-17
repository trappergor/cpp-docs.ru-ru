---
title: Целевые объекты | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- targets, specifying in NMAKE
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: edb75258c548526c68ed33f7f8037656750f6855
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713810"
---
# <a name="targets"></a>Целевые объекты

В строке зависимость, укажите один или несколько целевых объектов, используя любое допустимое имя файла, имени каталога или [псевдоцелью](../build/pseudotargets.md). Несколько целевых объектов отделяются с один или несколько пробелов или знаков табуляции. Целевые объекты не чувствительны к регистру. Разрешено указание путей с именами файлов. Целевой объект не может превышать 256 символов. Если целевой объект, предшествующую ему один символ, используйте разделяющий пробел. в противном случае NMAKE интерпретирует сочетание знаков как спецификатор диска.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

[Псевдоцелевые объекты](../build/pseudotargets.md)

[Несколько целевых объектов](../build/multiple-targets.md)

[Кумулятивные зависимости](../build/cumulative-dependencies.md)

[Целевые объекты в нескольких блоках описания](../build/targets-in-multiple-description-blocks.md)

[Побочные эффекты зависимостей](../build/dependency-side-effects.md)

## <a name="see-also"></a>См. также

[Блоки описания](../build/description-blocks.md)