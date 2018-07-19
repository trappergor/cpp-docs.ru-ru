---
title: Командная строка DUMPBIN | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- dumpbin
dev_langs:
- C++
helpviewer_keywords:
- DUMPBIN program, command line
ms.assetid: e6ad17d3-965d-41aa-9dfd-75bb073718d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc807a8f67ddaae894a0e0cba55475b804a0abce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32370518"
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