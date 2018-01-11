---
title: "Извлечение члена библиотеки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Lib
dev_langs: C++
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 38f45463bb76f858d1b88c059de57a4b8b86227e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="extracting-a-library-member"></a>Извлечение члена библиотеки
LIB можно использовать для создания Объектный OBJ-файл, содержащий копию элемента существующей библиотеки. Чтобы извлечь копию члена, используйте следующий синтаксис:  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 Эта команда создает OBJ-файл называется *objectfile* , содержащий копию `member` из *библиотеки*. `member` Имени учитывается регистр символов. Можно извлечь только один элемент в рамках одной команды. Параметр/out является обязательным; отсутствует имя вывода по умолчанию. Если файл с именем *objectfile* уже существует в указанном каталоге (или текущем каталоге, если каталог не указан с *objectfile*), извлеченный *objectfile*заменяет существующий файл.  
  
## <a name="see-also"></a>См. также  
 [Справочник по LIB](../../build/reference/lib-reference.md)