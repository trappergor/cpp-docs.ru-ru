---
title: "Командная строка DUMPBIN | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: dumpbin
dev_langs: C++
helpviewer_keywords: DUMPBIN program, command line
ms.assetid: e6ad17d3-965d-41aa-9dfd-75bb073718d4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7cf71e413cbdd505f10e86994811ed7648af86e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dumpbin-command-line"></a>Командная строка DUMPBIN
Чтобы запустить DUMPBIN, используйте следующий синтаксис:  
  
```  
DUMPBIN [options] files...  
```  
  
 Укажите один или несколько двоичных файлов, а также любые параметры, необходимые для управления данными. DUMPBIN отображает сведения в стандартный вывод. Можно перенаправить в файл или используйте параметр/out, чтобы указать имя файла для выходных данных.  
  
 При запуске программы DUMPBIN для файла без указания параметра DUMPBIN отображает параметра/Summary выходных данных.  
  
 При вводе команды `dumpbin` без любые другие данные в командной строке, DUMPBIN отображает сводную информацию об используемых параметрах.  
  
## <a name="see-also"></a>См. также  
 [Средства построения C/C++](../../build/reference/c-cpp-build-tools.md)   
 [Справочник DUMPBIN](../../build/reference/dumpbin-reference.md)