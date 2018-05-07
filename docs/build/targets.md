---
title: Целевые объекты | Документы Microsoft
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
ms.openlocfilehash: 79e9d72d2b2fb999d987a6781caace9a0360facb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="targets"></a>Целевые объекты
В строке зависимости можно определить один или несколько целевых объектов, используя любое допустимое имя файла, имя каталога, или [псевдоцелью](../build/pseudotargets.md). Несколько целевых объектов следует разделяйте пробелами или вкладки. Целевые объекты не учитывается регистр. Разрешено указание путей с именами файлов. Целевой объект не может превышать 256 символов. Если целевой объект, предшествующую ему один символ, используйте разделяющий пробел. в противном случае NMAKE интерпретирует сочетание знаков как спецификатор диска.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
 [Псевдоцелевые объекты](../build/pseudotargets.md)  
  
 [Несколько целевых объектов](../build/multiple-targets.md)  
  
 [Кумулятивные зависимости](../build/cumulative-dependencies.md)  
  
 [Целевые объекты в нескольких блоках описания](../build/targets-in-multiple-description-blocks.md)  
  
 [Побочные эффекты зависимостей](../build/dependency-side-effects.md)  
  
## <a name="see-also"></a>См. также  
 [Блоки описания](../build/description-blocks.md)