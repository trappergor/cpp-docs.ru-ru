---
title: "Использование нескольких встроенных файлов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 412c68f4d1279fea7969b3ddfdd2bf82e3cdbc47
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="multiple-inline-files"></a>Использование нескольких встроенных файлов
Команду можно создать несколько встроенных файлов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      command << <<  
inlinetext  
<<[KEEP | NOKEEP]  
inlinetext  
<<[KEEP | NOKEEP]  
```  
  
## <a name="remarks"></a>Примечания  
 Для каждого файла укажите один или несколько строк встроенного текста, следуют закрывающая строка, содержащая разделитель. Начало второй файл текст строки, следующей за разделяющей строкой первого файла.  
  
## <a name="see-also"></a>См. также  
 [Подставляемые файлы в Makefile](../build/inline-files-in-a-makefile.md)