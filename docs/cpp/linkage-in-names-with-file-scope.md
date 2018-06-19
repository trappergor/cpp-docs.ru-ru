---
title: Компоновка в именах в области видимости файла | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- static modifier, file scope
- static names and file scope
- file scope [C++]
- declarations [C++], external
- external linkage, scope linkage rules
- static variables, external declarations
ms.assetid: 38d3fa5e-1861-466e-a590-84b86f7b184e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 770b30516d16cf9ffccaae4724b368ca8fa33be0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419785"
---
# <a name="linkage-in-names-with-file-scope"></a>Компоновка в именах в области файлов
Перечисленные ниже правила компоновки относятся к именам (кроме имен `typedef` и перечислителей) с областью видимости файла.  
  
-   Если имя явно объявляется как **статических**, он имеет внутреннюю компоновку и определяет элемент программы внутри своей записи преобразования.  
  
-   Имена перечислителей и имена `typedef` не имеют компоновки.  
  
-   Все другие имена с областью видимости файла имеют внешнюю компоновку.  
  
 **Блок, относящийся только к системам Microsoft**  
  
-   Если имя функции с областью видимости файла явно объявляется как **встроенного**, он имеет внешнюю компоновку, если при создании или связан его адрес. Таким образом, функция с областью видимости файла может иметь внутреннюю или внешнюю компоновку.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
 Класс имеет внутреннюю компоновку, если он:  
  
-   не использует никаких функций C++ (например, элемент управления доступом к членам, функции-члены, конструкторы, деструкторы и т. д);  
  
-   не используется в объявлении другого имени, имеющего внешнюю компоновку. Это ограничение означает, что объекты типа класса, передаваемые функциям с внешней компоновкой, приводят к тому, что класс имеет внешнюю компоновку.  
  
## <a name="see-also"></a>См. также  
 [Программа и компоновка](../cpp/program-and-linkage-cpp.md)