---
title: Извлечение члена библиотеки | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0dc0dc67a6d9e4a3ff61aa3b82ac10b9eabcb94b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="extracting-a-library-member"></a>Извлечение члена библиотеки
LIB можно использовать для создания Объектный OBJ-файл, содержащий копию элемента существующей библиотеки. Чтобы извлечь копию члена, используйте следующий синтаксис:  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 Эта команда создает OBJ-файл называется *objectfile* , содержащий копию `member` из *библиотеки*. `member` Имени учитывается регистр символов. Можно извлечь только один элемент в рамках одной команды. Параметр/out является обязательным; отсутствует имя вывода по умолчанию. Если файл с именем *objectfile* уже существует в указанном каталоге (или текущем каталоге, если каталог не указан с *objectfile*), извлеченный *objectfile*заменяет существующий файл.  
  
## <a name="see-also"></a>См. также  
 [Справочник по LIB](../../build/reference/lib-reference.md)