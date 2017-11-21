---
title: "Класс basic_iostream | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
dev_langs: C++
helpviewer_keywords: basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 434ff6c2e3c65fae26492e85c63e94abc572f602
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="basiciostream-class"></a>Класс basic_iostream
Класс потока, поддерживающий ввод и вывод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_iostream : public basic_istream<Elem, Tr>,  
    public basic_ostream<Elem, Tr>  
{  
public:  
    explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

    virtual ~basic_iostream();

};  
```  
  
## <a name="remarks"></a>Примечания  
 Этот класс шаблона описывает объект, управляющий вставками с помощью базового класса [basic_ostream](../standard-library/basic-ostream-class.md)< `Elem`, `Tr`> и извлечениями с помощью базового класса [basic_istream](../standard-library/basic-istream-class.md)< `Elem`, `Tr`>. У этих двух объектов общий виртуальный базовый класс [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, `Tr`>. Они также управляют общим буфером потока с элементами типа `Elem`, признаки символов которых определяются классом `Tr`. Конструктор инициализирует базовые классы с помощью `basic_istream`( **strbuf**) и `basic_ostream`( **strbuf**).  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[basic_iostream](#basic_iostream)|Создание объекта `basic_iostream`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[swap](#swap)|Меняет местами содержимое предоставленного объекта `basic_iostream` на содержимое этого объекта.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[operator=](#op_eq)|Присваивает значение указанного объекта `basic_iostream` этому объекту. Это назначение перемещения, включающее `rvalue`, которое не оставляет копию.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<istream>  
  
 **Пространство имен:** std  
  
##  <a name="basic_iostream"></a>  basic_iostream::basic_iostream  
 Создание объекта `basic_iostream`.  
  
```  
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```  
  
### <a name="parameters"></a>Параметры  
 `strbuf`  
 Существующий объект `basic_streambuf`.  
  
 `right`  
 Существующий объект `basic_iostream`, который используется для создания нового объекта `basic_iostream`.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует базовые объекты посредством `basic_istream(strbuf)` и `basic_ostream(strbuf)`.  
  
 Второй конструктор инициализирует базовые объекты путем вызова `move(right)`.  
  
##  <a name="op_eq"></a>  basic_iostream::operator=  
 Присваивает значение указанного объекта `basic_iostream` этому объекту. Это назначение перемещения, включающее rvalue, которое не оставляет копию.  
  
```  
basic_iostream& operator=(basic_iostream&& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Ссылка `rvalue` на объект `basic_iostream`, на основе которого будет присвоено значение.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член вызывает `swap(right)`.  
  
##  <a name="swap"></a>  basic_iostream::swap  
 Меняет местами содержимое предоставленного объекта `basic_iostream` на содержимое этого объекта.  
  
```  
void swap(basic_iostream& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Объект `basic_iostream` для обмена.  
  
### <a name="remarks"></a>Примечания  
 Функция-член вызывает `swap(right)`.  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)

