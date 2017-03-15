---
title: "Ошибка средств компоновщика LNK1112 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1112
dev_langs:
- C++
helpviewer_keywords:
- LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4d404bc6e07a4e709ebab3859a9404795614e39f
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk1112"></a>Ошибка средств компоновщика LNK1112
тип компьютера модуля "type1" противоречит типу целевого компьютера "type1"  
  
 Объектные файлы, указанные как входные, скомпилированы для разных типов компьютеров.  
  
 Например, при попытке связать объектный файл, скомпилированный с помощью **/clr** , и объектный файл, скомпилированный с помощью **/clr:pure** (тип компьютера CEE), компоновщик создаст ошибку LNK1112.  
  
 Аналогично Если создать один модуль с [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] компилятора и другой модуль с x86 компилятора и попытке связать их, компоновщик создаст ошибку LNK1112.  
  
 Возможные причины этой ошибки: при разработке 64-разрядного приложения не установлен один из 64-разрядных компиляторов Visual C++. В этом случае 64-разрядные конфигурации будут недоступны. Чтобы устранить эту проблему, запустите установщик для Visual Studio и установите недостающие компоненты C++.  
  
 Эта ошибка также может возникать при изменении **активной конфигурации решения** в **диспетчере конфигураций** и последующей попытке построения проекта до удаления промежуточных файлов проекта. Чтобы устранить эту ошибку, выберите в меню **Сборка** пункт **Перестроить решение** . Можно также выбрать в меню **Сборка** пункт **Очистить решение** , а затем выполнить сборку решения.  
  
## <a name="see-also"></a>См. также  
 [Ошибки и предупреждения инструментов компоновщика](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
