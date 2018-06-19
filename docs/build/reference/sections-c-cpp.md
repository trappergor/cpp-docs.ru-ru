---
title: РАЗДЕЛЫ (C/C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- SECTIONS
dev_langs:
- C++
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c433bf49ee4c56833ac7291bcc4a0f90e32f4e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377304"
---
# <a name="sections-cc"></a>Ключевое слово SECTIONS (C/C++)
Представляет раздел одного или нескольких `definitions` , которые описатели доступа для разделов выходного файла проекта.  
  
```  
SECTIONS  
definitions  
```  
  
## <a name="remarks"></a>Примечания  
 Каждое определение должно находиться в отдельной строке. `SECTIONS` Ключевое слово может располагаться на одной строке с первым определением или на предыдущей строке. DEF-файл может содержать один или несколько `SECTIONS` инструкции.  
  
 Это `SECTIONS` инструкция задает атрибуты для одного или нескольких разделов в файле образа и может использоваться для переопределения атрибутов по умолчанию для каждого типа раздела.  
  
 Формат для `definitions` является:  
  
 `.section_name specifier`  
  
 где `.section_name` имя раздела образа программы и `specifier` — один или несколько из следующих модификаторов доступа:  
  
|Модификатор|Описание|  
|--------------|-----------------|  
|`EXECUTE`|Секция является исполняемой|  
|`READ`|Позволяет выполнять операции чтения данных|  
|`SHARED`|Секция совместно используется всеми процессами, загрузить изображение|  
|`WRITE`|Позволяет выполнять операции записи данных|  
  
 Разделяйте имена описатель пробелами. Пример:  
  
```  
SECTIONS  
.rdata READ WRITE  
```  
  
 `SECTIONS` Отмечает начало списка раздела `definitions`. Каждый `definition` должны находиться в отдельной строке. `SECTIONS` Ключевое слово может быть в той же строке, что и первый `definition` или на предыдущей строке. DEF-файл может содержать один или несколько `SECTIONS` инструкции. `SEGMENTS` Ключевое слово поддерживается как синоним для `SECTIONS`.  
  
 Поддерживается в предыдущих версиях Visual C++:  
  
```  
section [CLASS 'classname'] specifier  
```  
  
 `CLASS` Ключевое слово поддерживается для совместимости, но игнорируется.  
  
 Эквивалентный способ указание атрибутов секции — [/SECTION](../../build/reference/section-specify-section-attributes.md) параметр.  
  
## <a name="see-also"></a>См. также  
 [Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)