---
title: "Компоновка в именах в области видимости файла | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 581d7798f4f3aaa409d843f8b7f3b5869b47407e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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