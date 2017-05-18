---
title: "Потоки ввода | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- input streams
- input stream objects
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 344c0c29531ee44445b89f14396593cdd48a25ad
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="input-streams"></a>Потоки ввода
Объект потока ввода является источником байтов. Тремя наиболее важными классами потоков ввода являются [istream](../standard-library/basic-istream-class.md), [ifstream](../standard-library/basic-ifstream-class.md) и [istringstream](../standard-library/basic-istringstream-class.md).  
  
 Класс `istream` рекомендуется использовать для последовательного текстового ввода. Можно настроить объекты класса `istream` для работы с буферизацией или без буферизации. Все функции базового класса `ios` включены в `istream`. Создание объектов из класса `istream` будет выполняться редко. Вместо этого, обычно будет использоваться предопределенный объект `cin`, который является объектом класса [ostream](../standard-library/basic-ostream-class.md). В некоторых случаях после запуска программы `cin` можно присвоить другим объектам потока.  
  
 Класс `ifstream` поддерживает ввод в файлы на диске. Если вам требуется файл на диске только для ввода, создайте объект класса `ifstream`. Можно указать двоичные или текстовые данные. Если в конструкторе указать имя файла, этот файл автоматически открывается при создании объекта. В противном случае можно использовать функцию `open` после вызова конструктора по умолчанию. К объектам `ifstream` применяются много параметров форматирования и функций-членов. Все функции базовых классов `ios` и `istream` включены в `ifstream`.  
  
 Подобно функции библиотеки `sscanf_s`, класс `istringstream` поддерживает ввод из строк в памяти. Для извлечения данных из массива символов, который имеет завершающий нуль-символ, выделите и инициализируйте строку, а затем создайте объект класса `istringstream`.  
  
## <a name="in-this-section"></a>Содержание  
 [Построение объектов потока ввода](../standard-library/constructing-input-stream-objects.md)  
  
 [Использование операторов извлечения](../standard-library/using-extraction-operators.md)  
  
 [Проверка на наличие ошибок извлечения](../standard-library/testing-for-extraction-errors.md)  
  
 [Манипуляторы входных потоков](../standard-library/input-stream-manipulators.md)  
  
 [Функции-члены входного потока](../standard-library/input-stream-member-functions.md)  
  
 [Перегрузка оператора >> для собственных классов](../standard-library/overloading-the-input-operator-for-your-own-classes.md)  
  
## <a name="see-also"></a>См. также  
 [Программирование iostream](../standard-library/iostream-programming.md)

