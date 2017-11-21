---
title: "Псевдоцелевые объекты | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b018cd586e48f344b93b31571ba60ae9982ad4fe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="pseudotargets"></a>Псевдоцелевые объекты
Псевдоцелевые объекты — метка, используемая вместо имени файла в строке зависимости. Он интерпретируется как файл, который не существует и поэтому является устаревшей. NMAKE предполагает, что отметка времени псевдоцелью является наиболее актуальной всех зависимых элементов. Если у приложения нет зависимых элементов, используется текущее время. Если псевдоцелевой объект используется в качестве целевого объекта, его команды выполняются всегда. Псевдоцелевой объект, используемый в качестве зависимого также должен использоваться в качестве целевого в другой зависимости. Тем не менее Эта зависимость не требуется блок команд.  
  
 Имена псевдоцелью соответствовать правилам синтаксиса filename для целевых объектов. Тем не менее если имя не указано расширение (то есть, не содержащие точки), он может превышать 8 знаков имен файлов и может содержать до 256 символов.  
  
## <a name="see-also"></a>См. также  
 [Целевые объекты](../build/targets.md)