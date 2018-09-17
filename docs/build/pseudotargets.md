---
title: Псевдоцелевые объекты | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56c0c0c93163759b604352a6e623f15726b8e7ec
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715836"
---
# <a name="pseudotargets"></a>Псевдоцелевые объекты

Псевдоцелевые объекты — метка, используемая вместо имени файла в строке зависимость. Он интерпретируется как файл, который не существует и поэтому является устаревшей. NMAKE предполагается, что метка времени псевдоцелью представляет самую последнюю из всех его зависимых элементах. Если у него есть нет зависимых элементов, считается текущее время. Если псевдоцелью используется в качестве целевого объекта, его команды выполняются всегда. Псевдоцелевой, используемый в качестве зависимого, также должны использоваться в качестве целевого в еще одной зависимости. Тем не менее Эта зависимость не требуется блок команд.

Псевдоцелью имена следуют правилам синтаксис имени файла для целевых объектов. Тем не менее если имя не является расширением (то есть не содержит точку), он может превышать ограничение в 8 знаков для имен файлов и может содержать до 256 символов.

## <a name="see-also"></a>См. также

[Целевые объекты](../build/targets.md)