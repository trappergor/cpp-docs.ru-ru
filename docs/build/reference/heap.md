---
title: "-HEAP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /heap
dev_langs: C++
helpviewer_keywords:
- heap allocation, setting heap size
- HEAP editbin option
- -HEAP editbin option
- /HEAP editbin option
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 709b9a1b57750db4ea8eb13bdaa3d49eed9b7629
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="heap"></a>/HEAP
Задает размер кучи в байтах. Этот параметр применяется только к исполняемым файлам.  
  
```  
  
/HEAP:  
reserve[,commit]  
```  
  
## <a name="remarks"></a>Примечания  
 `reserve` Аргумент задает общее начальное выделение кучи в виртуальной памяти. По умолчанию размер кучи равен 1 МБ. [Справочник ЕDITBIN](../../build/reference/editbin-reference.md) Округляет указанное значение до ближайшего числа, кратного 4 байта.  
  
 Необязательный `commit` аргумент интерпретируется операционной системой. В операционной системе Windows он указывает начальный объем физической памяти для выделения и объем дополнительной памяти для выделения кучи необходимо развернуть. Выделенная виртуальная память резервирует пространство в файле подкачки. Более высокий `commit` значение позволяет системе выделения памяти меньше часто в том случае, когда приложению требуется больше пространства кучи, но увеличивает требования к памяти и, возможно, во время запуска приложения. `commit` Значение должно быть меньше или равно `reserve` значение.  
  
 Укажите `reserve` и `commit` значений в десятичное или шестнадцатеричное или восьмеричное нотации языка. Например значение 1 МБ можно указать как 1048576 в десятичном, или 0x100000 в шестнадцатеричном формате или 04000000 в восьмеричной.  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)