---
title: "Ошибка BSCMAKE BK1503 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1503
dev_langs: C++
helpviewer_keywords: BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86f2b6d282857409cdb1e1d49e04775e9886cde4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1503"></a>Ошибка BSCMAKE BK1503
не удается записать файл «имя_файла» [: причина]  
  
 BSCMAKE совмещает SBR-файлы, созданные во время компиляции, в одну базу данных браузера. Если базы данных превышает 64 МБ или если число входных SBR-файлов превышает 4092, будут выдаваться ошибки.  
  
 Если проблема вызвана превышает 4092 SBR-файлов, необходимо уменьшить количество входных файлов. В Visual Studio это можно добиться путем [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) всего проекта, то повторной проверки на основе файла в файл.  
  
 Если проблема вызвана BSC-файл, размер которых превышает 64 МБ, уменьшение числа SBR-файлы в качестве входного приведет к уменьшению объема получившийся BSC-файл. Кроме того объем данных просмотра можно уменьшить /Em (исключить символы расширения макросов), /El (исключить локальные переменные) и /Es (исключить системные файлы).  
  
## <a name="see-also"></a>См. также  
 [Параметры BSCMAKE](../../build/reference/bscmake-options.md)