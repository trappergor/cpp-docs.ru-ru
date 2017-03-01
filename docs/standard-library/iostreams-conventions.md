---
title: "Соглашения iostreams | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- iostream header
- C++ Standard Library, iostreams
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 247f9948c6f22e7d24c47966a398d1b33e054f45
ms.lasthandoff: 02/24/2017

---
# <a name="iostreams-conventions"></a>Соглашения iostreams
Заголовки iostreams поддерживают преобразования между текстом и закодированными формами, а также ввод и вывод во внешние файлы.  
  
|||  
|-|-|  
|[\<fstream>](../standard-library/fstream.md)|[\<iomanip>](../standard-library/iomanip.md)|  
|[\<ios>](../standard-library/ios.md)|[\<iosfwd>](../standard-library/iosfwd.md)|  
|[\<iostream>](../standard-library/iostream.md)|[\<istream>](../standard-library/istream.md)|  
|[\<ostream>](../standard-library/ostream.md)|[\<sstream>](../standard-library/sstream.md)|  
|[\<streambuf>](../standard-library/streambuf.md)|[\<strstream>](../standard-library/strstream.md)|  
  
 В самом простом способе использования iostreams достаточно включить заголовок [\<iostream>](../standard-library/iostream.md). После этого можно извлечь значения из [cin](../standard-library/iostream.md#cin) или [wcin](../standard-library/iostream.md#wcin) для чтения из стандартного ввода. Правила для этого приведены в описании класса [basic_istream](../standard-library/basic-istream-class.md). Вы также можете вставить значения в [cout](../standard-library/iostream.md#cout) или [wcout](../standard-library/iostream.md#wcout) для записи в стандартный вывод. Правила для этого приведены в описании класса [basic_ostream](../standard-library/basic-ostream-class.md). Контроль формата для средств извлечения и средств вставки выполняется с помощью класса [класс basic_ios](../standard-library/basic-ios-class.md). Обработка этой информации о формате извлекающих и вставляющих объектов относится к области нескольких манипуляторов.  
  
 Вы можете выполнить те же операции iostreams с файлами, которые вы открываете по имени, с помощью классов, объявленных в [\<fstream>](../standard-library/fstream.md). Для преобразования между iostreams и объектами класса [basic_string Class](../standard-library/basic-string-class.md) используйте классы, объявленные в [\<sstream>](../standard-library/sstream.md). Чтобы сделать то же самое со строками C, используйте классы, объявленные в [\<strstream>](../standard-library/strstream.md).  
  
 Остальные заголовки обеспечивают вспомогательные службы, обычно интересные только самым опытным пользователям классов iostreams.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


