---
title: целевые объекты
ms.date: 11/04/2016
helpviewer_keywords:
- targets, specifying in NMAKE
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
ms.openlocfilehash: 4bb80b01993ee3f3715f551c73337cf24cd43f2c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826623"
---
# <a name="targets"></a>целевые объекты

В строке зависимость, укажите один или несколько целевых объектов, используя любое допустимое имя файла, имени каталога или [псевдоцелью](pseudotargets.md). Несколько целевых объектов отделяются с один или несколько пробелов или знаков табуляции. Целевые объекты не чувствительны к регистру. Разрешено указание путей с именами файлов. Целевой объект не может превышать 256 символов. Если целевой объект, предшествующую ему один символ, используйте разделяющий пробел. в противном случае NMAKE интерпретирует сочетание знаков как спецификатор диска.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

[Псевдоцелевые объекты](pseudotargets.md)

[Несколько целевых объектов](multiple-targets.md)

[Кумулятивные зависимости](cumulative-dependencies.md)

[Целевые объекты в нескольких блоках описания](targets-in-multiple-description-blocks.md)

[Побочные эффекты зависимостей](dependency-side-effects.md)

## <a name="see-also"></a>См. также

[Блоки описания](description-blocks.md)