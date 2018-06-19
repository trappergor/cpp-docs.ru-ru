---
title: . RES-файлы как входные данные компоновщика | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RES files as linker input
- .res files as linker input
- linking [C++], resource files
- resource files, linking
ms.assetid: 9c37ab00-97df-4d9a-91cd-6bf132970683
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 71344bb752ff7a328ddd5f718a5de1c1f42b65be
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32370671"
---
# <a name="res-files-as-linker-input"></a>RES-файлы в качестве входных файлов компоновщика
При компоновке программы можно указать RES-файл. RES-файл создается компилятором ресурсов (RC). LINK автоматически преобразует RES-файлы в формат COFF. Средство CVTRES.exe должен быть в том же каталоге, что и LINK.exe, или в каталоге, указанном в переменной среды PATH.  
  
## <a name="see-also"></a>См. также  
 [Входные LINK-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)