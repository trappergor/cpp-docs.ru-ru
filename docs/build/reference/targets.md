---
title: Целевые объекты
ms.date: 11/04/2016
helpviewer_keywords:
- targets, specifying in NMAKE
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
ms.openlocfilehash: 52b2f3293b97955b605e2821102247f506c2950b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317657"
---
# <a name="targets"></a>Целевые объекты

В строке зависимость, укажите один или несколько целевых объектов, используя любое допустимое имя файла, имени каталога или [псевдоцелью](pseudotargets.md). Несколько целевых объектов отделяются с один или несколько пробелов или знаков табуляции. Целевые объекты не чувствительны к регистру. Разрешено указание путей с именами файлов. Целевой объект не может превышать 256 символов. Если целевой объект, предшествующую ему один символ, используйте разделяющий пробел. в противном случае NMAKE интерпретирует сочетание знаков как спецификатор диска.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

[Псевдоцелевые объекты](pseudotargets.md)

[Несколько целевых объектов](multiple-targets.md)

[Кумулятивные зависимости](cumulative-dependencies.md)

[Целевые объекты в нескольких блоках описания](targets-in-multiple-description-blocks.md)

[Побочные эффекты зависимостей](dependency-side-effects.md)

## <a name="see-also"></a>См. также

[Блоки описания](description-blocks.md)