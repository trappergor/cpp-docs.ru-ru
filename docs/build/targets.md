---
title: "Целевые объекты | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- targets, specifying in NMAKE
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a07947dc7de4529d8cef3aa0f104d529d0b95ea5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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