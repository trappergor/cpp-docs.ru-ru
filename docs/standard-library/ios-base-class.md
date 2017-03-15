---
title: "Класс ios_base | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ios_base"
  - "std.ios_base"
  - "std::ios_base"
  - "xiosbase/std::ios_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ios_base - класс"
ms.assetid: 0f9e0abc-f70f-49bc-aa1f-003859f56cfe
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс ios_base
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот класс описывает хранилище и функции\-члены общие для обоих потоков \(ввода и вывода\), не зависящих от параметров шаблона.  \(Класс шаблона [basic\_ios](../Topic/basic_ios%20Class.md) описывает общие принципы и зависит от параметров шаблона.\)  
  
 Объект класса ios\_base хранит сведения о форматировании, состоящие из следующих элементов:  
  
-   Флаги форматирования в объекте типа [fmtflags](../Topic/ios_base::fmtflags.md).  
  
-   Маска исключения в объекте типа [iostate](../Topic/ios_base::iostate.md).  
  
-   Ширина поля в объекте типа `int`*.*  
  
-   Точность отображения в объекте типа `int`.  
  
-   Объект языкового стандарта в объекте типа **locale**.  
  
-   Два расширенных массива с элементами типа **long** и указателем `void`.  
  
 Объект класса ios\_base также хранит сведения о состоянии потока в объекте типа [iostate](../Topic/ios_base::iostate.md) и стеке обратных вызовов.  
  
### Конструкторы  
  
|||  
|-|-|  
|[ios\_base](../Topic/ios_base::ios_base.md)|Создает объект `ios_base`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[event\_callback](../Topic/ios_base::event_callback.md)|Описывает функцию, передаваемую в [register\_call](../Topic/ios_base::register_callback.md).|  
|[fmtflags](../Topic/ios_base::fmtflags.md)|Константы для указания внешнего вида выходных данных.|  
|[iostate](../Topic/ios_base::iostate.md)|Определяет константы, описывающие состояние потока.|  
|[openmode](../Topic/ios_base::openmode.md)|Описывает процесс взаимодействия с потоком.|  
|[seekdir](../Topic/ios_base::seekdir.md)|Задает начальную точку для операций смещения.|  
  
### Перечислимые типы  
  
|||  
|-|-|  
|[событие](../Topic/ios_base::event.md)|Задает типы событий.|  
  
### Константы  
  
|||  
|-|-|  
|[adjustfield](../Topic/ios_base::fmtflags.md)|Битовая маска, определенная как `internal` &#124; `left` &#124; `right`.|  
|[app](../Topic/ios_base::openmode.md)|Задает поиск до конца потока перед каждой вставкой.|  
|[ate](../Topic/ios_base::openmode.md)|Задает поиск до конца потока при первом создании его управляющего объекта.|  
|[badbit](../Topic/ios_base::iostate.md)|Регистрирует потерю целостности буфера потока.|  
|[basefield](../Topic/ios_base::fmtflags.md)|Битовая маска, определенная как `dec` &#124; `hex` &#124; `oct`.|  
|[beg](../Topic/ios_base::seekdir.md)|Задает поиск относительно начала последовательности.|  
|[двоичные](../Topic/ios_base::openmode.md)|Указывает, что файл должен быть считан как двоичный, а не текстовый поток.|  
|[boolalpha](../Topic/ios_base::fmtflags.md)|Задает вставку или извлечение объектов типа `bool` в качестве имен \(таких как `true` и `false`\), а не числовых значений.|  
|[cur](../Topic/ios_base::seekdir.md)|Задает поиск относительно текущей позиции в последовательности.|  
|[dec](../Topic/ios_base::fmtflags.md)|Задает вставку или извлечение целочисленных значений в десятичном формате.|  
|[end](../Topic/ios_base::seekdir.md)|Задает поиск относительно конца последовательности.|  
|[eofbit](../Topic/ios_base::iostate.md)|Регистрирует конец файла при извлечении из потока.|  
|[failbit](../Topic/ios_base::iostate.md)|Регистрирует сбой при извлечении допустимого поля из потока.|  
|[зафиксировать](../Topic/ios_base::fmtflags.md)|Задает вставку значений с плавающей запятой в формате с фиксированной запятой \(без поля экспоненты\).|  
|[floatfield](../Topic/ios_base::fmtflags.md)|Битовая маска, определенная как `fixed` &#124; `scientific`|  
|[goodbit](../Topic/ios_base::iostate.md)|Очищает все биты состояния.|  
|[hex](../Topic/ios_base::fmtflags.md)|Задает вставку или извлечение целочисленных значений в шестнадцатеричном формате.|  
|[в](../Topic/ios_base::openmode.md)|Задает извлечение из потока.|  
|[internal](../Topic/ios_base::fmtflags.md)|Выполняет заполнение по ширине поля, вставляя символы заполнения в точке внутри созданного числового поля.|  
|[left](../Topic/ios_base::fmtflags.md)|Задает выравнивание по левому краю.|  
|[oct](../Topic/ios_base::fmtflags.md)|Задает вставку или извлечение целочисленных значений в восьмеричном формате.|  
|[выходной](../Topic/ios_base::openmode.md)|Задает вставку в поток.|  
|[справа](../Topic/ios_base::fmtflags.md)|Задает выравнивание по правому краю.|  
|[экспоненциальный](../Topic/ios_base::fmtflags.md)|Задает вставку значений с плавающей запятой в экспоненциальном формате \(с полем экспоненты\).|  
|[showbase](../Topic/ios_base::fmtflags.md)|Задает вставку префикса, отображающего базу созданного целочисленного поля.|  
|[showpoint](../Topic/ios_base::fmtflags.md)|Задает безусловную вставку десятичной запятой в созданное поле с плавающей запятой.|  
|[showpos](../Topic/ios_base::fmtflags.md)|Задает вставку знака плюс в созданное неотрицательное числовое поле.|  
|[skipws](../Topic/ios_base::fmtflags.md)|Задает пропуск начальных пробелов перед определенными извлечениями.|  
|[trunc](../Topic/ios_base::openmode.md)|Задает удаление содержимого существующего файла при создании его управляющего объекта.|  
|[unitbuf](../Topic/ios_base::fmtflags.md)|Обеспечивает запись выходных данных на диск после каждой вставки.|  
|[прописные](../Topic/ios_base::fmtflags.md)|Задает вставку эквивалентных прописных букв для букв нижнего регистра в определенных вставках.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[сбой](../Topic/ios_base::failure.md)|Класс членов служит базовым классом для всех исключений, выдаваемых функцией\-членом [clear](../Topic/basic_ios::clear.md) в классе шаблона [basic\_ios](../Topic/basic_ios%20Class.md).|  
|[флаги](../Topic/ios_base::flags.md)|Задает или возвращает текущие параметры флага.|  
|[getloc](../Topic/ios_base::getloc.md)|Возвращает сохраненный объект языкового стандарта.|  
|[imbue](../Topic/ios_base::imbue.md)|Изменяет языковой стандарт.|  
|[Init](../Topic/ios_base::Init.md)|Создает стандартные объекты iostream при построении.|  
|[iword](../Topic/ios_base::iword.md)|Присваивает значение, сохраняемое в виде `iword`.|  
|[точность](../Topic/ios_base::precision.md)|Задает количество цифр для отображения числа с плавающей запятой.|  
|[pword](../Topic/ios_base::pword.md)|Присваивает значение, сохраняемое в виде `pword`.|  
|[register\_callback](../Topic/ios_base::register_callback.md)|Задает функцию обратного вызова.|  
|[setf](../Topic/ios_base::setf.md)|Задает указанные флаги.|  
|[sync\_with\_stdio](../Topic/ios_base::sync_with_stdio.md)|Гарантирует, что операции с iostream и библиотекой времени выполнения C выполняются в том порядке, в котором они расположены в исходном коде.|  
|[unsetf](../Topic/ios_base::unsetf.md)|Отключает указанные флаги.|  
|[ширина](../Topic/ios_base::width.md)|Задает длину потока вывода.|  
|[xalloc](../Topic/ios_base::xalloc.md)|Указывает, что переменная должна быть частью потока.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator \=](../Topic/ios_base::operator=.md)|Оператор присваивания для объектов `ios_base`.|  
  
## Требования  
 **Заголовок:** \<ios\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)