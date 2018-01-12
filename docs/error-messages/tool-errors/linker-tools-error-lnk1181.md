---
title: "Ошибка средств компоновщика LNK1181 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1181
dev_langs: C++
helpviewer_keywords: LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8f5092d4f3ce7b4f96ca4dc5c1554483a7fc3a0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1181"></a>Ошибка средств компоновщика LNK1181
не удается открыть входной файл «имя_файла»  
  
 Не удалось найти компоновщик `filename` , так как он не существует или путь не найден.  
  
 Некоторые наиболее распространенные причины возникновения ошибки LNK1181:  
  
-   `filename`указывается как дополнительную зависимость в строке компоновщика, но файл не существует.  
  
-   Объект **/LIBPATH** инструкцию, которая указывает на каталог, содержащий `filename` отсутствует.  
  
 Чтобы устранить проблемы, описанные выше, убедитесь, что все файлы, указанные в строке компоновщика присутствуют в системе.  Также убедитесь, что **/LIBPATH** инструкции для каждого каталога, содержащего компоновщику файл.  
  
 Другая возможная причина LNK1181 является то, что длинное имя файла имеет пробелы не заключен в кавычки.  В этом случае компоновщик будет распознают только имя файла до первого пробела и предполагается, что расширение файла. obj.  Решением может стать — заключить длинное имя файла (путь и имя файла) в кавычки.  
  
 Дополнительные сведения см. в разделе [LIB-файлы в качестве входных данных компоновщика](../../build/reference/dot-lib-files-as-linker-input.md).  
  
## <a name="see-also"></a>См. также  
 [/ LIBPATH (дополнительный параметр Libpath)](../../build/reference/libpath-additional-libpath.md)