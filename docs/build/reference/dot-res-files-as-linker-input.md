---
title: ". RES-файлы как входные данные компоновщика | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- RES files as linker input
- .res files as linker input
- linking [C++], resource files
- resource files, linking
ms.assetid: 9c37ab00-97df-4d9a-91cd-6bf132970683
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ac4dedc419c28b4e68d7dcc1772f176738580b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="res-files-as-linker-input"></a>RES-файлы в качестве входных файлов компоновщика
При компоновке программы можно указать RES-файл. RES-файл создается компилятором ресурсов (RC). LINK автоматически преобразует RES-файлы в формат COFF. Средство CVTRES.exe должен быть в том же каталоге, что и LINK.exe, или в каталоге, указанном в переменной среды PATH.  
  
## <a name="see-also"></a>См. также  
 [Входные LINK-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)