---
title: "Псевдоцелевые объекты | Документы Microsoft"
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
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 761b71f05840c86516563df79d45cc1bb018fbba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="pseudotargets"></a>Псевдоцелевые объекты
Псевдоцелевые объекты — метка, используемая вместо имени файла в строке зависимости. Он интерпретируется как файл, который не существует и поэтому является устаревшей. NMAKE предполагает, что отметка времени псевдоцелью является наиболее актуальной всех зависимых элементов. Если у приложения нет зависимых элементов, используется текущее время. Если псевдоцелевой объект используется в качестве целевого объекта, его команды выполняются всегда. Псевдоцелевой объект, используемый в качестве зависимого также должен использоваться в качестве целевого в другой зависимости. Тем не менее Эта зависимость не требуется блок команд.  
  
 Имена псевдоцелью соответствовать правилам синтаксиса filename для целевых объектов. Тем не менее если имя не указано расширение (то есть, не содержащие точки), он может превышать 8 знаков имен файлов и может содержать до 256 символов.  
  
## <a name="see-also"></a>См. также  
 [Целевые объекты](../build/targets.md)